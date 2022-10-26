# Rendering the zipcheck 
There are two modes of rending the zipcheck:

## Minified
The zipcheck will only display the address lookup, and redirect the user to a different page to where the full zipcheck will be implementen. To enable the stand-alone mode, you simply have to provide the URL to the page the form needs to redirect to, by using the `redirect` prop.

```
<nextpertise-zipcheck 
    redirect="/results"
 ></nextpertise-zipcheck>
```

## Full
In full mode, the zipcheck will display both the address lookup form, and the results page. Furthermore, the user will not be redirected, but both compoments will communicate without the page refreshing

# Passing properties from a custom form / using a custom form
You can also choose to implemenent a custom form on, though we can't give support, we can give a little support on how-to do so.
The component will read the following url-parameters:
1) zipcheck-zipcode
2) zipcheck-housenr
3) zipcheck-ext

If any are available, the compoment will pre-fill the values from the given parameters.

By example, you can use a custom form somewhere the prompts the user for this information, and then redirects to the page using the information provided.

```
<form 
    method="GET"
    action="/results" # The URL of the page where you've implemented the module
    autocomplete="false"
    >
          <input type="text"
             name="zipcheck-zipcode"
             placeholder="Zipcode"
             maxlength="7">
             
          <input 
              type="text"
              placeholder="House Number"
              name="zipcheck-housenr">
              
         <input
                 placeholder="House Number Extension"
                 name="zipcheck-ext">
</form>
```

# Customizing the layout
You can pass properties to the compoment to customize the layout. Below is a full example with descriptions:

```
<nextpertise-zipcheck 
    primary-color="#0070ba" 
    secondary-color="#00A2D7" 
    background-color="#eff8fd" 
    token="" #api token
    input-border-top-color="#D4E6F3"  # The color of the top border, leave the same color as input-bg to disable
    input-background-color="#fff" # Background for the inputs
    redirect="/results" # See Minified mode 
    >
</nextpertise-zipcheck>
```
