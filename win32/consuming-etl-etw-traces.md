# Consuming an ETW trace session of ETL trace file

The API to consume either a real-time trace session or a previous session from a etl file involves three main API calls:
- OpenTrace - is called to set up a structure that tells the system where the trace info is and where is your callback function to handle trace events
- ProcessTrace - starts the processing 
- CloseTrace - cleanup any resources used to process the trace
