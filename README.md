## Repository for networking team

This repository has networking helm packages 

### helm package list 
```
- [ipsec_service] https://ankush06.github.io/nw/ipsec_service-0.0.1.tgz 
```

### Adding repository to the client

Follow below steps to add the repostry on client
```
#add repository and update it
helm repo add mynw1 https://ankush06.github.io/nw
helm repo update

#aditional commands
#list helm repository 
helm repo list
#search package in repository
helm search repo ipsec
```
```
### Deploying service
helm install ipsec_app mynw1/ipsec_service
```

### Updating helm chart
```
#Download helm:
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh

#configure global git config
git config --global user.name "ankush06"
git config --global user.email "adianzx@gmail.com"
#verify git global config
git config --global --list

#clone the dir
git clone https://github.com/ankush06/nw.git && cd nw/

#update the chart changes
#verify the changes
helm  lint src/ipsec_service/
#Create the Helm chart package
helm package src/*

#Push the git repository on GitHub
git add . 
git commit -m "my chart changes"
git push origin master                                              

```


