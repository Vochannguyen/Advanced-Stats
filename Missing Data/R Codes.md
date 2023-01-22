
# Approach #1 - Deleting
## Remove / Delete Datasets
+ data_clean1 = na.omit(data) - Deletes
+ dim(data_clean1) - Finds New Dimensions
+ vis_miss(data_clean1) - Checks for Missing Data after Deleting


# Approach #2 - Imputing
## Imputing Data
+ impute.median.info<-preProcess(data[,-c(1,11)],method="medianImpute") - Step 1: Find Medians
+ data_clean2<-predict(impute.median.info,newdata=data) - Set dataset to median into
+ Step 3: Check dimensions - dim(data_clean2)
+ step 4: Look at a graph of missing values - vis_miss(data_clean2)


# Approach #3 - Impute using Bagg Trees
## Imputing Data
+ Step 1: Similar to approach 2, just find medians impute.bag.info<-preProcess(data[,-c(1,11)],method="bagImpute")
+ Step 2: data_clean3<-predict(impute.bag.info,newdata=data)
+ Step 3: Check Dimensions: dim(data_clean3)
+ Step 4: Look at missing value son graph: vis_miss(data_clean3)

# Approach #4 - Impute using KNN
## Impute Data (Choose K)
+ Step 1: Use the preProcess but change method : **impute.knn.info<-preProcess(data[,-c(1,11)],method="knnImpute",k=5,knnSummary=mean)**
+ data_clean4<-predict(impute.knn.info,newdata=data)
+ dim(data_clean4)
+ vis_miss(data_clean4)
+ head(data_clean4)  #See the z-scoring
