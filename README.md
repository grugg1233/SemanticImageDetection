# SemanticImageDetection
Used Yolo 26 to fine tune a carparts seg to ood rav 4 youtube video - created custom merged dataset that used manually labeled examples to significantly increase predictive accuracy for  OOD car review videos 


#  Image-to-Video Semantic Retrieval via Object Detection

**Instructions on how to run the code**

I have pushed just the best.pt weights file to the github under models/ data can be retrieved by running all the following

```bash 
sudo apt update && sudo apt install -y ffmpeg
pip install yt-dlp

ffmpeg -version
yt-dlp --version

mkdir -p data ; cd data 

yt-dlp -f "bestvideo[ext=mp4]+bestaudio[ext=m4a]/best[ext=mp4]" \
  -o "input_video.mp4" \
  "https://www.youtube.com/watch?v=YcvECxtXoxQ"

 mkdir -p data/frames ffmpeg -i input_video.mp4 -vf "fps=1, scale=1280:-1" frames/frame_%05d.jpg

```


**Instructions on how to run any tests (if applicable)**

All tests are written into the code and results have been manually compiled into the report and parquet files have been added to : https://huggingface.co/datasets/grugg/CS370-A2-rav4-video-retrieval-Attallah

**Instructions on how to run any notebook (if applicable)**

the notebook should be mostly functional with these set up (however be sure to check for model = YOLO("model/best.pt") and model.predict(source="data/frames")) as without the above or changing those values (where they are not already present) you will run into issues



