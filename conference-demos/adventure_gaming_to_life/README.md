# (Work in progress) Bringing Adventure Gaming to Life on the AI PC with the OpenVINO™ toolkit

Authors: Arisha Kumar, Garth Long, Ria Cheruvu, Dmitriy Pastushenkov, Paula Ramos, Raymond Lo, Zhuo Wu

Contact: Ria Cheruvu, Dmitriy Pastushenkov

Tested on: Intel® Core™ Ultra 7 and 9 Processors

![Pipeline OCR](https://github.com/openvinotoolkit/openvino_notebooks/assets/22090501/8999027b-21e2-419d-95c4-b8a70534fc82)

# Installation

1. Clone this repository to get started

2. Download and optimize required models
	- Nano-Llava (MultiModal) - Dice Recognition 
	- Whisper - Speech Recognition
	- Llama3-8b-instruct - Prompt Refinement
	- AI Superesolution - Increase res of generated image
	- Latent Consistency Models - Generating Image
    
	```
    python -m venv model_installation_venv
	model_installation_venv\Scripts\activate
	pip install -r python3.12_requirements_model_installation.txt
	python download_and_prepare_models.py
    ``` 
	After model installation, you can remove the virtual environment as it isn't needed anymore.


3. Create a virtual env and install the required python packages <br>
    ```
    python -m venv dnd_env
	dnd_env\Scripts\activate
	pip install -r requirements.txt 
	pip install "openai-whisper==20231117" --extra-index-url https://download.pytorch.org/whl/cpu

    ``` 

4. Open a terminal or you can use the existing one with dnd_env environment activated and run the audio server - <br>
```
python audio_server.py
```
5. Open another terminal, activate another dnd_env virtual environment and start the Gradio GUI - <br>
```
python gradio_ui.py
```
Click on the web link to open the GUI in the web browser <br>

# How to Use 🛣️
There are two flows you can follow to interact with the GUI:

### (Step 1 - *Option 1* 🎲) 
Set OCR to true and roll a die! Take a snapshot using the Gradio Image interface. After recognizing the die, the system will try to output the correct die value, and a special location associated with the number you rolled (see locations.json for the list), to add a theme to your prompts. You can change this and the corresponding theme it sets.
### (Step 1 - *Option 2* 📷)
Set OCR to False, and take a picture via the Gradio image interface of any object you want! Your "theme" will become the image description.
### (Step 2 🗣️) Speak your prompt
Start the recording, and wait till the server is listening to begin speaking your prompt to life. Click the Stop button to stop the generation.
### (Step 3 ➕) Add theme to prompt
Now, your prompt is transcribed! Click on the "Add Theme to Prompt" button to combine your prompt and theme.
### (Step 4 ⚙️) Refine it with an LLM
You can optionally ask an LLM model to refine your model by clicking on the LLM button. It will try its best to generate a prompt infusing the elements (although it does hallucinate at times).
### (Step 5 🪄🖼️) Generate your image
Click "Generate Image" to see your image come to life! Feel free to adjust the advanced parameters to control the image generation model!
