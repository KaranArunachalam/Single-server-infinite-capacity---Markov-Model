# Single server with infinite capacity (M/M/1):(oo/FIFO)
## Aim :
To find (a) average number of materials in the system (b) average number of materials in the conveyor (c) waiting time of each material in the system (d) waiting time of each material in the conveyor, if the arrival  of materials follow poisson process with the mean interval time 12 seconds, serivice time of lathe machine follows exponential distribution with mean serice time 1 second and average service time of robot is 7seconds.

## Software required :
Visual components and Python

## Theory:
Queuing are the most frequently encountered problems in everyday life. For example, queue at a cafeteria, library, bank, etc. Common to all of these cases are the arrivals of objects requiring service and the attendant delays when the service mechanism is busy. Waiting lines cannot be eliminated completely, but suitable techniques can be used to reduce the waiting time of an object in the system. A long waiting line may result in loss of customers to an organization. Waiting time can be reduced by providing additional service facilities, but it may result in an increase in the idle time of the service mechanism.

![image](1.png)

This is a queuing model in which the arrival is Marcovian and departure distribution is also Marcovian,number of server is one and size of the queue is also Marcovian,no.of server is one and size of the queue is infinite and service discipline is 1st come 1st serve(FCFS) and the calling source is also finite.

## Procedure :

![image](2.png)



## Experiment:
![image](https://private-user-images.githubusercontent.com/93427522/240579349-2960ee3e-7325-4e09-85e1-ae816ceaaab3.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE3MDM0MjkyMzIsIm5iZiI6MTcwMzQyODkzMiwicGF0aCI6Ii85MzQyNzUyMi8yNDA1NzkzNDktMjk2MGVlM2UtNzMyNS00ZTA5LTg1ZTEtYWU4MTZjZWFhYWIzLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEyMjQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMjI0VDE0NDIxMlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTllMDkwYTgzNjY4ZDZmMTRjYWVmOTJkNDBkMTFkMmMyZDAwYTAyYzdiN2MyN2VlZmU2NWJjMTI0MzI4N2I5ZDAmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.YRHwE5Xg3O65mbKmLN71THLQE7Uns3Lhu5hHQrDRBrY)
![image](https://private-user-images.githubusercontent.com/93427522/240579443-f5b111fa-a1b3-47ce-b862-a071560beec0.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE3MDM0MjkyMzIsIm5iZiI6MTcwMzQyODkzMiwicGF0aCI6Ii85MzQyNzUyMi8yNDA1Nzk0NDMtZjViMTExZmEtYTFiMy00N2NlLWI4NjItYTA3MTU2MGJlZWMwLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEyMjQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMjI0VDE0NDIxMlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTA4ZDYyNzE5YmMxYjE5ZDMzYzAzZTBiOGVmMzYyNjFmNDU0ZTcwYWYyODEzMzA2NDU3OWY0YWU3YTFiNGI4ZjkmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.csAeq8R3mcocf4rnz_HkMku7Y0ZvhXKjBkEyNhK2F_I)

 
## Program
```
arr_time=float(input("Enter the mean inter arrival time of objects from Feeder (in secs): "))
ser_time=float(input("Enter the mean  inter service time of Lathe Machine (in secs) :  "))
Robot_time=float(input("Enter the Additional time taken for the Robot (in secs) :  "))
lam=1/arr_time
mu=1/(ser_time+Robot_time)
print("--------------------------------------------------------------")
print("Single Server with Infinite Capacity - (M/M/1):(oo/FIFO)")
print("--------------------------------------------------------------")
print("The mean arrival rate per second : %0.2f "%lam)
print("The mean service rate per second : %0.2f "%mu)
if (lam <  mu):
    Ls=lam/(mu-lam)
    Lq=Ls-lam/mu
    Ws=Ls/lam
    Wq=Lq/lam
    print("Average number of objects in the system : %0.2f "%Ls)
    print("Average number of objects in the conveyor :  %0.2f "%Lq)
    print("Average waiting time of an object in the system : %0.2f secs"%Ws)
    print("Average waiting time of an object in the conveyor : %0.2f secs"%Wq)
    print("Probability that the system is busy : %0.2f "%(lam/mu) )
    print("Probability that the system is empty : %0.2f "%(1-lam/mu) )
else:
    print("Warning! Objects Over flow will happen in the conveyor")
print("---------------------------------------------------------------")
```

## Output :
![image](https://private-user-images.githubusercontent.com/93427522/240579638-56a83ac2-cbd6-41e5-a0ab-788d37c1160d.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE3MDM0MjkyMzIsIm5iZiI6MTcwMzQyODkzMiwicGF0aCI6Ii85MzQyNzUyMi8yNDA1Nzk2MzgtNTZhODNhYzItY2JkNi00MWU1LWEwYWItNzg4ZDM3YzExNjBkLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFJV05KWUFYNENTVkVINTNBJTJGMjAyMzEyMjQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjMxMjI0VDE0NDIxMlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTQ2YWI0Y2JiMTVmODI2YTg1ODkyMGEwMmRjZTNkYzQ4NmJhZjE3ODRkZDYyODgxMjRhZjM2ODAwYTNlYzc3MzYmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.9Q7Bba9ptRUh6OFznhTCfGuKv4FTAeSZ9hL46Ennyik)

## Result :

The average number of material in the sysytem and in the conveyor and waiting time are successfully found.