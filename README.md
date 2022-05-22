# Beyza
First, we keep the start time at the beginning of our file so that we can calculate the CPU time.
Since the first facility opened in the problem is requested to be made according to the one median problem, I open a oneMedian method in order to find the first facility opening. 
This method checks the distanceMatrixes between the facility and the points so that we can find the index of the facility with the smallest sum.
Since the number of facilities in the file given to us is 5 for the beginning, we assumed that 5 facilities will be opened.
I define a heuristic method to find opened facilities. This heuristic method takes the number of facilities, facilities, points, that is, customers and distanceMatrix as parameters.
We scan until the desired number of facilities are opened in the method. 
What we control until the desired number of facilities are opened is again the situation of checking the distance I defined in an abc method and saving the opened facilitiy. 
We scan the distance of the facilities from the points until we reach the P number, and if we can find a shorter distance within the opened facilities, we update the closest facility and the closest distance to that point.
Since we can find the facility with the closest distance, we start to fill the openedFacilities ArrayList with the index of that facility.
I open a customerAssignments method in order to find out which customer meets the demand from which facility, and also to examine the demand-supply relationship.
In order to find assignments made to customers, there is a need for facilities, points and distances, as well as the facilities that I found with the help of previous methods.
There are three states we have for demand and supply. I try to examine these three cases in the method. 
Our first option might be greater than supply demand. If this option is realized, the demand of the mentioned customer will be met and we must extract the amount we use from the supply.
Our second option might be less than supply demand. As a result of this situation, the supply owned by the facility is reset and therefore we do not need to process this facility any further. Since we do not have enough, customer demand is not fully met. We remove the part that is met and perform a scan again for that customer through the facilities.
In our third and last option, supply and demand can be equal. As a result of this situation, the demand of that customer is fully met. The Facility's supply hits zero, so we remove that facility because we can't process it any further.
I see that a missing point when making Custemor assignments is to find the facility closest to that customer, and for this reason, I open a method called pointNearestFacility and have the closest facility found. I find the closest distance among the provided facilities and keep the index of the closest one.
I see that I also need an end time to calculate CPU time, and I record the CPU time where our assignments end.
At the same time, I print the assignment HashMap that we keep in order to see which customer has benefited from which facility.
