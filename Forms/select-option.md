## select option

html:
```
<!-- perpage -->
<select class="mr-1 form-control form-control-sm rounded bright" style="border:none" ng-change="vm.setlimit()" ng-model="vm.perpage">
  <option ng-selected="vm.perpage == i" ng-repeat="i in vm.ppages" value="{{i | number}}">{{i}}</option>
</select>
```

js
```
//set perpage
if($cookies.get('perpage')==undefined){
  vm.perpage = 10;
}else{
  vm.perpage = $cookies.get('perpage');
}
vm.ppages = [5,10,20,30,50,100];

```

change:
```
//change limit
vm.setlimit = ()=>{
  $cookies.put('perpage',vm.perpage);
  //getfiles(conf,api,vm);
}
```
