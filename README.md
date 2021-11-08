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

- You can create a new module with `next g module <module-name>`

## Controllers

- handle incoming **requests** and returning **responses** to the client
- bound to a specific path, for example `/tasks`
- contain **handlers**, which handle **endpoints** and **request methods** (GET, POST, DELETE, etc)
- can take advantage of **dependency injection** to consume providers within the same module

### Controller definition

- defined by decorating a class with the **@Controller** decorator
- the decorator accepts a string, which is the **path** to be handled by the controller

```typescript
@Controller("/tasks")
export class TaskController {}
```

### Handler definition

- methods within the controller class, decorated with decorators such as **@Get**, **@Post**, etc

```typescript
@Controller("/tasks")
export class TaskController {
  @Get()
  getAllTasks() {
    return;
  }

  @Post()
  createTask() {
    return;
  }
}
```
