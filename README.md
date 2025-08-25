# backend
from fastapi import FastAPI, UploadFile, File, Form
from fastapi.responses import JSONResponse

app = FastAPI()


@app.get("/")
async def root():
    return {"message": "Backend is running successfully!"}


@app.post("/summarize_me")
async def summarize_me(bio: str = Form(...)):
    return {"summary": "Placeholder summary"}


@app.post("/analyze_resume")
async def analyze_resume(file: UploadFile = File(...)):
    # In a real scenario, you would process the uploaded file here
    return {
        "strengths": ["Placeholder strength 1", "Placeholder strength 2"],
        "weaknesses": ["Placeholder weakness 1", "Placeholder weakness 2"],
        "missing_keywords": ["Placeholder keyword 1", "Placeholder keyword 2"]
    }


@app.post("/career_match")
async def career_match(role: str = Form(...)):
    return {"match": "Placeholder career match result"}


@app.post("/career_advice")
async def career_advice(goal: str = Form(...)):
    return {"advice": "Placeholder advice"}
