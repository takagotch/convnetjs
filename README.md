### convnetjs
---
https://github.com/karpathy/convnetjs

```js
var layer_defs = [];
layer_defs.push({{type: 'input', out_sx:1, out_sy:1, out_depth:2});
layer_defs.push({type: 'fc', num_neuraons:20, activation:'relu'});
layer_defs.push({type: 'softmax', num_classes:10});

var net = new convnetjs.Net([0.3, -0.5]);
net.makeLayers(layer_defs);

var x = new convnetjs.Vol([0.3, -0.5]);
var prob = net.forward(x);

console.log('probability that x is class 0: ' + prob.w[0]);
var trainer = new convnetjs.SGDTrainer(net, {learning_rate:0.02, 12_decay:0.001});
trainer.train(x, 0);

var prob2 = net.forward(x);
console.log('probability that x is class 0: ' + prob2.w[0]);

var layer_defs = [];
layer_defs.push({type:'input', out_sx:32, out_sy:32, out_depth:3});
layer_defs.push({type:'conv', sx:4, filters:16, stride:1, pad:2, activation:'relu'});
layer_defs.push({type:'pool', sx:2, stride:2});
layer_defs.push({type:'conv', sx:5, filters:20, stride:1, pad:2, activation:'relu'});
layer_defs.push({type:'pool', sx:2, stride: 2});
layer_defs.push({type:'conv', sx: 5, filters:20, stride:1, pad:2, activatin:'relu'});
layer_defs.push({type:'pool', sx:2, stride:2});
layer_defs.push({type:'softmax', num_classes:10});

net = new convnetjs.Net();
net.makeLayers(layer_defs);

var x = convnetjs.img_to_vol(document.getElementById('dome_image'))
var output_probabilities_vol = net.forward(x)

```

```
ant -lib yuicompressor-2.4.8.jar -f build.xml
```

```
```


