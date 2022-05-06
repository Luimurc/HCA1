# HCA1
Test1
#Carga de Paquetes
require(DeclareDesign)
set.seed(10101) 
n_samp<-3
mod_edad <-
  declare_model(N = 100, age = sample(0:80, size = N, replace = TRUE)) +
  declare_inquiry(mean_age = mean(age)) +
  declare_sampling(S = complete_rs(N = N, n = n_samp)) +
  declare_estimator(age ~ 1, model = lm) 
