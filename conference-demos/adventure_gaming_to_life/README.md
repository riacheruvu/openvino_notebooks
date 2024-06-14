# (Work in progress) Bringing Adventure Gaming to Life on the AI PC with the OpenVINO™ toolkit

Authors: Arisha Kumar, Garth Long, Ria Cheruvu, Dmitriy Pastushenkov, Paula Ramos, Raymond Lo, Zhuo Wu

Contact: Ria Cheruvu, Dmitriy Pastushenkov

Tested on: Intel® Core™ Ultra 7 and 9 Processors

![Pipeline OCR](https://github.com/openvinotoolkit/openvino_notebooks/assets/22090501/8999027b-21e2-419d-95c4-b8a70534fc82)

# Installation

1. Clone this repository to get started

2. Create a virtual env and install the required python packages <br>
    ```
    	python -m venv dnd_env
	dnd_env\Scripts\activate
	pip install -r requirements.txt 
	pip install "openai-whisper==20231117" --extra-index-url https://download.pytorch.org/whl/cpu

    ``` 
3. Download the required models and place them in a folder titled dnd_mdels:
	- Nano-Llava (MultiModal) - Dice Recognition 
	- Whisper - Speech Recognition
	- Llama3-8b-instruct - Prompt Refinement
	- AI Superesolution - Increase res of generated image
	- Latent Consistency Models - Generating Image

Steps for download TBD

4. Open a terminal or you can use the existing one with dnd_env environment activated and run the audio server - <br>
```
python audio_server.py
```
5. Open another terminal, activate another dnd_env virtual environment and start the Gradio GUI - <br>
```
python gradio_ui.py
```

Click on the web link to open the GUI in the web browser <br>