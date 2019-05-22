# Getting started

Simplify your inputs in React with inputhooks

    npm i --save inputhooks

Just import the lib

    import useInput from 'inputhooks'

And build your forms easily

    const nameInputHook = useInput('John Doe')

    render(){

        return(
            <>
                <input {...nameInputHook}/>
            </>
        )
    }

Access to the value with :

    nameInputHook.value

## Config

You can auto load/save your hook in localstorage with :

    const nameInputHook = useInput('John Doe',{
        localStorage:'data-name'
    })

and sessionstorage with :

    const nameInputHook = useInput('John Doe',{
        sessionStorage:'data-name'
    })

## Validation

It's also possible to set a validation function :

    const nameInputHook = useInput('',{
        validation: (value) => value.length > 2
    })

You can import from inputhooks some validation functions :

    import useInput, {NOT_NULL, MAIL_VALID} from 'inputhooks'

and use them like that :

    const nameInputHook = useInput('',{
        validation: NOT_NULL
    })

## Formatting

    You can format user input with :

    const nameInputHook = useInput('John Doe', {
        inputPatch: value => value.toLowerCase()
    })

    then the value nameInputHook.value will be lowercased.

    You can also format output with :

    const nameInputHook = useInput('John Doe', {
        outputPatch: value => value.toLowerCase()
    })

    the lowercased value will be displayed but the value of nameInputHook.value isn't modified.

## Helper

The function allValid helps to know if every inputhook are valid :

    import { allValid } from 'inputhooks'

and just use the function like that :

    const valid = allValid( nameInputHook, lastnameInputhook )
