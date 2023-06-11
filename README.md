# lwcErrorHandling
Generic component to handle LWC errors and show them in sticky banner form.
The repo contains just the lwc component needed.

# --------- How-to guide --------- 

## A. How to deploy

1. Download the repo.
2. Extract the downloaded zip
3. Put the "lwcErrorHandling" folder in main/default/lwc folder of your vs code project
4. Select the default org in you VS Code.
5. Right click on the "lwcErrorHandling" folder in VS Code explorer pane and deploy it to your salesforce org.

How to use in your components as child component to make it work:

## B. Edit your parent LWC component:

write these lines of code in your  

### B.1 Parent LWC component's HTML file 
```
     <template if:true={error}>
        <c-lwc-error-handling error={error} onerrorclosed={handleError}></c-lwc-error-handling>
     </template>
```

### B.2 Parent LWC component's js file 
```
    // handle error from child components
    errorCallback(error, stack){
        this.error = error;
    }
    
    // handle errors from self (submit button press)
    handleFormError(event){
        this.error = event.detail;
    }
    
    // handle errors from self
    handleError(error){
        this.error =  error;   
    }
```
