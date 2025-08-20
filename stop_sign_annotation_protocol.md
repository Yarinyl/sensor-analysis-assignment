# Stop Sign Annotation Protocol
## Introduction:
Hello and thank you for contributing to our labeling effort.
Thanks to you, we will be able to predict more precisely the likelihood of an accident to occur and hopefully give the drivers tools to avoid them.

The goal is to label dashcam videos to capture how drivers behave when approaching, stopping at, and leaving stop signs.

## Data:
You will be given one short (35–45 seconds) video taken from a car dashboard. The video has no sound, and there is not any additional meta-data available to you during the annotation.
Each video consists of an interaction of the driver with a stop sign, thus including at least 5 seconds before arriving at the stop sign as well as after passing it.

## Your Task:
For each video your task is to determine the following features **regarding the ego-vehicle (the car with the dashcam)**:
- StopSignCheck: Yes / No - Whether video includes an interaction with a stop sign.
- StopSignVisible: Yes / No - Whether the stop sign was visible (or obstructed in any way).
- StoppedFully: Yes / No - Whether the driver comes to a complete halt (0 motion for ≥2 sec).
- StopLocation: Before line / On line / Past line - Where the driver stops regarding the line of the stop sign.
- OtherVehiclesPresent: Yes / No - Whether there were other vehicles stoping before the driver reached the stop sign (which makes him stop).
- PedestriansPresent: Yes / No - Whether there were pedestrians passing before the driver reached the stop sign (which makes him stop).
- Lighting: Day / Night / Dusk-Dawn - What was the lighting condition in the scene.

## General Guidelines:
- It is recommended to watch the video at least twice when determining the value of the labels. You can slow down the playing speed if needed.
- Make sure that your annotation is referring the ego-vehicle (the car with the dashcam).
- If a situation is unclear, do not guess. Mark it as Ambiguous and leave a note.
- Avoid assumptions about driver intent. Label only observable behavior.
- All data must be treated as confidential. Do not share, download, or discuss videos outside the annotation tool.
- If multiple stop signs are present, annotate only the one relevant to the ego-vehicle. If more than one is relevant to the ego-vehicle, annotate the first encountered.

# Additional information (not part of the protocol)

## Assumptions or Tradeoffs:
- Assumed a “complete stop” is defined as 0 motion for ≥2 seconds.
- Assumes other drivers’ actions are irrelevant unless they influence context.
- Assumes only the first stop sign is relevant in multi-sign intersections.
- Tradeoff - By including a larger set of features rather than fewer, we aim to capture richer training signals, though at the cost of slower annotation speed.
- Tradeoff - By defin stop (≥2s = full stop) we ensure consistency but can misclassify borderline cases.

## Explanation:
The labeling scheme provides structured supervision by capturing both driver actions (e.g., full stop, stop location) and contextual conditions (e.g., traffic, visibility).
This design reduces annotation noise, ensures consistency across annotators, and equips the model to learn fine-grained behavioral cues, enabling training an effective model to analyze driver behavior around stop
signs.