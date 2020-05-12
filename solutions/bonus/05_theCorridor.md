# 05_theCorridor.md

## pppery: The Trapbreaker
Define an object that destroys traps and just push it through them.
```javascript
map.defineObject("trapbreaker", {
    "symbol":"t",
    "type":"dynamic",
    "projectile":true,
    "pushable":true,
    "onDestroy":function(me) {
        map.placeObject(me.getX(),me.getY()-1,"trapbreaker");
    }
});
var player = map.getPlayer()
map.placeObject(player.getX(),player.getY()-1,"trapbreaker");
```

## fdalvi: Change the trap behaviour
Just redefine the `trap_behaviour` function to do nothing, and you can just walk through to the exit.
```javascript
function trap_behaviour (me, left, right) {
}
```
