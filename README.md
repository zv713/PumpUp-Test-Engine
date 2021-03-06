# PumpUp Test Engine based on Vanilla Engine Template

## Documentation

### Mac/Linux
1. open the terminal and cd to the PredictionIO/bin directory(if you don't have PredictionIO installed see https://docs.prediction.io/install/)
2. run "pio-start-all" (this assumes you're using hBase and ElasticSearch)
3. run "pio status" to make sure everything is running correctly
4. run "git clone https://github.com/zv713/PumpUp-Test-Engine \<EngineName\>" while in the PredictionIO/bin directory where \<EngineName\> can be any name you choose when done, cd to this newly created directory
5. run "pio app new \<MyApp\>" where \<MyApp\> can be any name you choose and copy the Access Key of the app created from the terminal output Note: you can run "pio app list" later if you forget the Access Key
6. run "python data/import_eventserver.py --access_key \<access_key\>" where \<access_key\> is the access key of the app created in 5. This will create some sample events in the Event Server. Note if you don't have python installed you'll need to run "sudo easy_install predictionio"
7. in the newly created engine directory you'll find a file named "engine.json". Open it and change the "appName" parameters from "MyApp" to whatever you named your app in step 5.
8. Run "pio build --verbose" which may take a while the first time PredictionIO is used
9. Run "pio train"
10. Run "pio deploy" and open a new terminal window when that's done, without closing the initial one
11. In the new terminal you can query the engine by calling in the usual fashion for example: curl -H "Content-Type: application/json" -d '{ "lastPostId": 4, "limit": 2 }' http://localhost:8000/queries.json feel free to change the limit and lastPostId parameters as you'd like
12. Once you're done, make sure to press "control + C" and then run "pio-stop-all" in the initial terminal
window, to stop and close the engine and PredictionIO.


## Versions

### v0.1.0

- initial version
