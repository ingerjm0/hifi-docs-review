---
title: 'JavaScript Tips & Tricks'
taxonomy:
  category: docs
---
High Fidelity's robust [JavaScript API](../../api-reference) provides the tools for you to build great content and user experiences in VR. We've compiled some advanced JavaScript tips you can use while scripting for High Fidelity. 

**On This Page:**

+ [Compute 3D Math Operations](#compute-3d-math-operations)
+ [Include External JS and JSON Files](#include-external-js-and-json-files)

## Compute 3D Math Operations 

When you script for VR worlds like High Fidelity, you need 3D math operations to compute the position and orientation of 3D objects in-world. We cannot simply add two vectors. To script 3D math operations, you can use the following namespaces in our JavaScript API:

+ [Vec3](../../api-reference/namespaces/vec3): The Vec3 API has facilities for generating and manipulating 3-dimensional vectors. 
+ [Quat](../../api-reference/namespaces/quat): The Quat API provides facilities for generating and manipulating quaternions. 

## Include External JS and JSON Files

When writing a script in High Fidelity, you might need to access the methods or objects in an external JS file or get information from a JSON file. For example, if you're writing a script to make your avatar wave, you might need to use some methods that already exist in an external JS file. You can do this using the `require` method in the Scripts namespace of our API.

Any script that you try to retrieve using this method must export either a function or an object. Let's try this using an example. 

Create a JS script that you want to access from your main script. 

**example.js**

```javascript
module.exports = {
    sayHello: function () {
        console.log("Hello!");
    },
    sayGoodbye: function () {
        console.log("Goodbye!");
    }
};
```

In **example.js**, you are exporting two functions that print either Hello or Goodbye, depending on which function you call, to the console. Now, let's use `require` in your main script.

Create a JS script called **main.js**.

```javascript
var greet = Script.require(Script.resolvePath("example.js"));
greet.sayHello(); // prints Hello to the console
```

When you use the `require` method, you are making any function or object exported from **example.js** available to **main.js**. This means that **main.js **now has access to functions that will print either Hello or Goodbye to the console. In the above example, we are printing Hello to the console when we run **main.js**.

**See Also**

+ [Write Your Own Scripts](../write-scripts)
+ [API Reference](../../api-reference)