# dinamic-optional-field-yup


```js


export const createFinanceLeadSchema = yup.object().shape(
  {
    name: yup.string().required(required),
    companyName: yup.object().when('personTypeIsPF', {
      is: false,
      then: yup.string().required(required),
    }),
    email: yup
      .string()
      .email('E-mail inválido')
      .required(required)
      .oneOf(['email', 'phone'], 'Preencha pelo menos um campo'),
    phone: yup
      .string()
      .matches(phoneRegExp, 'Telefone inválido')
      .required(required)
      .oneOf(['email', 'phone'], 'Preencha pelo menos um campo'),
  },
  [['email', 'phone']],
)

```
