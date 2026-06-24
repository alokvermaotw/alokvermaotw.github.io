- E M Stands for Expectation Maximization.
- Better Clustering algorithm as compare to the KMeans
- Algorithm:
	- _Guessing_: Make guess of Means and Covariance of every cluster.
	- _Expectation_: Classify every observation in our data according to which cluster it's most likely to be member of, according to the most recent estimates of Means of Covariances.
	- _Maximization_: Use the classification obtained in the _Expectation_ step to calculate new estimates for Means and Covariances of each cluster.
	- _Convergence_: Repeat the expectation and Maximization step Until reaching a stopping condition.

```python
#initial guesses
mean1=[-1,0]
mean2=[0.5,-1]
mean3=[0.5,0.5]
allmeans=[mean1,mean2,mean3]
cov1=[[1,0],[0,1]]
cov2=[[1,0],[0,1]]
cov3=[[1,0],[0,1]]
allvar=[cov1,cov2,cov3]

# plot to see the points and guessed points
plt.plot(allxs, allys, 'x')
plt.plot(mean1[0],mean1[1],'r*', markersize=15)
plt.plot(mean2[0],mean2[1],'r*', markersize=15)
plt.plot(mean3[0],mean3[1],'r*', markersize=15)
plt.axis('equal')
plt.show()

# Expecation
def classify(allpts,allmns,allvar):
	vars=[]
	for n in range(len(allmns)):
		vars.append(multivariate_normal(mean=allmns[n], cov=a
		llvar[n]))
		classification=[]
		for point in allpts:
			this_classification=-1
			this_pdf=0
			for n in range(len(allmns)):
				if vars[n].pdf(point)>this_pdf:
				this_pdf=vars[n].pdf(point)
				this_classification=n+1
				classification.append(this_classification)
	return classification

theclass=classify(allpoints,allmeans,allvar)

def makeplot(allpoints,theclass,allmeans):
	thecolors=['black']*len(allpoints)
	for idx in range(len(thecolors)):
		if theclass[idx]==2:
			thecolors[idx]='green'
		if theclass[idx]==3:
			thecolors[idx]='yellow'
	allxs=[point[0] for point in allpoints]
	allys=[point[1] for point in allpoints]
	for i in range(len(allpoints)):
		plt.scatter(allxs[i], allys[i],color=thecolors[i])
	for i in range(len(allmeans)):
		plt.plot(allmeans[i][0],allmeans[i][1],'b*', markersi
	ze=15)
	plt.axis('equal')
	plt.show()

# Maximazation step
def getcenters(allpoints,theclass,k):
	centers=[]
	thevars=[]
	for n in range(k):
		pointsn=[allpoints[i] for i in range(0,len(allpoints)) if theclass[i]==(n+1)]
		xpointsn=[points[0] for points in pointsn]
		ypointsn=[points[1] for points in pointsn]
		xcenter=np.mean(xpointsn)
		ycenter=np.mean(ypointsn)
		centers.append([xcenter,ycenter])
		thevars.append(np.cov(xpointsn,ypointsn))
	return centers,thevars

allmeans,allvar=getcenters(allpoints,theclass,3)

theclass=classify(allpoints,allmeans,allvar)

# Convergence step
for n in range(0,100):
	theclass=classify(allpoints,allmeans,allvar)
	allmeans,allvar=getcenters(allpoints,theclass,3)

```