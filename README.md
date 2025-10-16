you can run like this ..

1 - make a virtual env first

2 - install all requirements 

3 - run the below command 


uvicorn app.main:app --reload

Deploying on Vercel
-------------------

This project includes a `Dockerfile` and `vercel.json` to deploy the app on Vercel using their Docker builder. Steps:

1. Install the Vercel CLI and login: `npm i -g vercel && vercel login`
2. From the project root (`tds-project-1-main`) run: `vercel` and follow prompts.
3. Ensure you set required environment variables (`GITHUB_TOKEN`, `GITHUB_USERNAME`, `OPENAI_API_KEY`, `USER_SECRET`) in the Vercel dashboard for the project.

Notes:
- Vercel will build the Docker image and run the service. The app exposes port 8000 internally.
- For evaluation callbacks, provide a public `evaluation_url` reachable by the deployed app (not `localhost`).


FOR TESTING:
use:
curl -i -X POST 'API-ENDPOINT-URL'   -H 'Content-Type: application/json'   -d '{"secret":"SECRET","email":"you@example.com","task":"final-test-task","round":1,"nonce":"n1","evaluation_url":"https://example.com/eval","brief":"Tissot Watch"}'
