# Gestió de Recursos (`res/`)

Tots els fitxers no executables (imatges, dissenys d'interfície, cadenes de text i colors) es guarden en el directori `res/`.

## Estructura de la Carpeta `res/`

* **`drawable/`:** Imatges vectorial (XML) o imatges en format PNG/JPEG.
* **`layout/`:** Fitxers XML de disseny d'interfície (*View System*).
* **`values/`:** Fitxers XML amb valors literals:
    * `strings.xml`: Texts traduebles i internacionalització.
    * `colors.xml`: Paleta de colors de l'aplicació.
    * `themes.xml`: Estils visuals globals.
* **`mipmap/`:** Icones de l'aplicació per a diferents densitats de pantalla (`hdpi`, `xhdpi`, `xxhdpi`).

## Exemple de Recursos de Text (`strings.xml`)

És una *bona pràctica* no escriure mai text directament en el codi, sinó utilitzar referències:

```xml
<resources>
    <string name="app_name">La meva Aplicació</string>
    <string name="welcome_message">Benvingut a la nostra aplicació Android!</string>
    <string name="btn_continue">Continuar</string>
</resources>
```

### Accés als Recursos

* Des del codi **Kotlin**:
  ` val text = getString(R.string.welcome_message) `
* Des d'un fitxer **XML**:
  ` android:text="@string/welcome_message" `

  ---
  **[Volver al Índice Principal](index.md)**
