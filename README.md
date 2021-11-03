# Nest Complete Course

## Install Nest

```bash
npm i -g @nestjs/cli
```

## Create a new project

```bash
nest new <project-name>
```

## Modules

- each app has at least one module - the root module
- this is the entry point of the app
- modules organize components by a closely related set of capabilities (features)
- it's good practice to have one folder per module
- modules are **singletons**
- modules can be imported by multiple other modules

### Module definition

- a module is defined by annotating a class with the **@Module** decorator
- the decorator provides metadata that Nets uses to organize the app structure

### @Module decorator properties

- **providers**: array of providers to be available within the module via dependency injection
- **controllers**: array of controllers to be instantiated within the module
- **exports**: array of providers to export to other modules
- **imports**: list of modules required by this module, any exported provider by these modules will now be available in our module via dependency injection
