# Using `npm link`
## Reason
When you're coding your module, you'll probably have a separate node application
you use as sandbox to see if your module is going well.
In those cases you won't want to publish and re-install your module every time
you change a comma. 

## Solution
To avoid these situations, `npm` provides a simple solucion.

### First step
You go into your modules directory and run:
>npm link

This will take your module's name from `package.json` and link you system
repository of packages with you directory using that name.

### Second Step
You go to your sandbox's directory and run:
>npm link <my-module-name>

And that's it, now your sandbox will stay connected to your module reflecting any
change you make.
