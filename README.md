# PhishingDetector_URLs_Texts_Docs
Website which takes URLs, texts and docs as inputs and gives us the confidence of that being a phishing one or legitimate one using machine learning models trained by me.

How to execute : 
1. Download the zip folder from the given drive link and extract it.
2. Open backend folder in termial and execute the command : uvicorn app.main:app --host 127.0.0.1 --port 8000 --reload
3. In new terminal window open frontend folder and execute the command : npm run dev
4. Now you can see the UI through your browser.

# Running our project without any dependencies.
As we have containerized our project so one can run our project directly without any dependencies, just you need to have docker engiene.
Steps : 
1. Create a dir/forlder to pull the project from dockerhub  
   mkdir campusshield-deploy
   cd campusshield-deploy
   nano docker-compose.yml
 
2. In docker-compose.yml file paste :  
   services:  
  backend:  
    image: theprateekmittal/campusshield-backend:latest  
    ports:  
      - "8000:8000"  
    restart: always  

  frontend:  
    image: theprateekmittal/campusshield-frontend:latest  
    ports:  
      - "80:80"  
    depends_on:  
      - backend  
    restart: always  

  3. Now stay in the folder and run the command : docker compose up -d  

And then you are just done and project will start. We have added this feature for easy deployments and portability.
