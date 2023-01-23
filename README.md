# dinamic-optional-field-yup


```js

import * as Yup from 'yup';

const schema = Yup.object().shape({
  phone: Yup.string()
    .when('email', {
      is: val => val && val.length > 0,  // if email is filled in
      then: Yup.string().notRequired(),  // phone number is not required
      otherwise: Yup.string().required('The phone number is required'), 
    }),
  email: Yup.string()
    .when('phone', {
      is: val => val && val.length > 0, // if phone is filled in
      then: Yup.string().notRequired(), // email is not required
      otherwise: Yup.string().required('The email is required'),
    }),
});


```
