# TP-angularJS
<!doctype html>
<html ng-app>
<head>
<script type="text/javascript">
    function ClotheController($scope){
        $scope.name=""
        $scope.clothes=['pull','chemise','echarpe'];
        $scope.addClothe=function(){
            $scope.clothes.push($scope.newClothe);
        }

        $scope.deleteClothe=function(index){
            $scope.clothes.splice(index, 1);
        }
    }
</script>
</head>
<body>
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/angularjs/1.0.1/angular.min.js"></script>
<div ng-controller="ClotheController">
    Entrez votre nom : <input type="text" ng-model="name">
    Selectionnez un vetement:
        <select ng-model="selectedClothe" ng-options="clothe for clothe in clothes">
        </select>
    <hr/>
    Liste des vetements :
    <ul>
        <li ng-repeat="clothe in clothes">{{clothe}} <a href ="https://www.google.fr/search?client=ubuntu&channel=fs&q={{clothe}}&ie=utf-8&oe=utf-8&gfe_rd=cr&ei=FebiVoPDFamx8wflnpnIDg"> {{clothe}} </a> {{$index}}
  <button ng-click="deleteClothe($index)">X</button>
        </li>
    </ul>
    <hr />
    Nom : {{name}}<br />
    Vetement choisi: {{selectedClothe}}
    <hr />
    Ajouter un vetement :
        <input type="text" ng-model="newClothe">
        <button ng-click="addClothe()">Add</button>
    
</div>
</body>
</html>
