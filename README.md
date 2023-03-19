# frontend

## Project setup
```
npm install
cd ./frontend
npm install -g @vue/cli
npm install bootstrap --save
```

### Compiles and hot-reloads for development
```
npm run serve (do not forget to run backend as well!)
If there is a data regarding the date that has been chose, then forecast data will be showen otherwise it means that in xml file there is no information regarding that date. Additionally, since case sensitive place filtering and hyphens/whitespaces have been implemented, you can search places such as Tartu, tartu,tarTu,tar-tu, tar tu.
```
frontend app runs at http://localhost:8081/ . If the port is the different when you run it, please update the path of @CrossOrigin in ForecastController.


#The logo that has been used for this app was taken from :
https://logovectordl.com/forecast-app-logo-vector-svg/
