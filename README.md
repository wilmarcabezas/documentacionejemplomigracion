# 📁 LoginView.xaml.cs

**LoginView.xaml.cs** localizado en el espacio de nombres  `Migracion.Enrolamiento.UI.Views`. Este archivo contiene la lógica de interacción para `LoginView UserControl`, que permite al usuario iniciar sesión ingresando su correo electrónico y contraseña.

## 📋 Tabla de contenido

- [Propiedades](#properties)
- [Eventos](#events)

## 📚 Propiedades

| Propiedades              | Tipo         | Descripcion                                      |
|--------------------------|---------------|--------------------------------------------------|
| DataContext              | object        | Representa el contexto de datos para UserControl. |
| PasswordErrorVisibility  | Visibility    | Obtiene o establece la visibilidad del mensaje de error de contraseña. |
| EmailErrorVisibility     | Visibility    | Obtiene o establece la visibilidad del mensaje de error del correo electrónico. |

## 🎉 Eventos

### TxtPassword_PasswordChanged

```csharp
private void TxtPassword_PasswordChanged(object sender, RoutedEventArgs e)
{
    if (DataContext is LoginViewModel vm)
    {
        if (sender is PasswordBox password)
        {
            if (!string.IsNullOrEmpty(password.Password))
                vm.PasswordErrorVisibility = Visibility.Collapsed;
            else
                vm.PasswordErrorVisibility = Visibility.Visible;
        }
    }
}
```

Este evento se activa cuando el usuario ingresa o cambia su contraseña en el cuadro de contraseña. 
Comprueba si el `DataContext` es del tipo `LoginViewModel` y si el cuadro de contraseña no está vacío. Si es así, `PasswordErrorVisibility`.  
La propiedad se establece en `Visibility.Collapsed`, lo que oculta el mensaje de error. Si el cuadro de contraseña está vacío, 
el La propiedad `PasswordErrorVisibility` se establece en `Visibility.Visible` y muestra el mensaje de error.

### TxtEmail_TextChanged

```csharp
private void TxtEmail_TextChanged(object sender, TextChangedEventArgs e)
{
    if (DataContext is LoginViewModel vm)
    {
        if (sender is TextBox textbox)
        {
            if (!string.IsNullOrEmpty(textbox.Text))
                vm.EmailErrorVisibility = Visibility.Collapsed;
            else
                vm.EmailErrorVisibility = Visibility.Visible;
        }
    }
}
```
Este evento se activa cuando el usuario ingresa o cambia su correo electrónico en el cuadro de texto del correo electrónico. 
Comprueba si el DataContext es del tipo `LoginViewModel` y si el cuadro de texto del correo electrónico no está vacío. Si es así, EmailErrorVisibility. La propiedad se establece en Visibility.Collapsed, lo que oculta el mensaje de error. Si el cuadro de texto del correo electrónico está vacío, el La propiedad EmailErrorVisibility se establece en Visibility.Visible y muestra el mensaje de error.
