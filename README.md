# Smooth Operator



We use smol-podcaster to take care of most of transcription work. What it will do for you:

- Generate a clean, diarized transcript of the podcast with speaker labels and timestamps
- Generate a list of chapters with timestamps for the episode
- Give you title ideas based on previous ones (modify the prompt to give examples of your own, it comes with Latent Space ones)
- Give you ideas for tweets to announce the podcast

### Environment Setup

Activate virtualenv with

`source venv/bin/activate`

Install dependencies with

`pip install -r requirements.txt`

Make a copy of the `.env.sample` and replace it with your keys:

`mv .env.sample .env`

### Run with web UI + background runs

If you want to run a bunch in parallel (or remotely) you can use the web UI + celery. Before running, you'll need a broker for celery 

If you have honcho installed, simply run `honcho start`, otherwise run each command manually:

```
celery -A tasks worker --loglevel=INFO
flask --app web.py --debug run
```
