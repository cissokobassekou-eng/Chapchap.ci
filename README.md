import cv2
import numpy as np

# Modèle de segmentation (ex. MediaPipe Selfie Segmentation)
import mediapipe as mp
segmenter = mp.solutions.selfie_segmentation.SelfieSegmentation(model_selection=1)

cap = cv2.VideoCapture(0)
while cap.isOpened():
    ok, frame = cap.read()
    if not ok:
        break
    rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    mask = segmenter.process(rgb).segmentation_mask
    mask = np.stack((mask,) * 3, axis=-1) > 0.5

    blurred = cv2.GaussianBlur(frame, (55, 55), 0)
    output = np.where(mask, frame, blurred)

    cv2.imshow("Flou d'arrière-plan", output)
    if cv2.waitKey(1) & 0xFF == ord("q"):
        break

cap.release()
cv2.destroyAllWindows()
