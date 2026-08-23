# fundamentos de prueba
Debemos conocer el proceso de negocio de la empresa y cuales son los clientes para tener el resultado esperado, recordando que la IA no conoce el proceso y puede asumir cosas vagas para complacer al usuario.

## Calidad de Software
Las pruebas se deben integrar desde el incio del desarrollo hasta el final. Para eso el equipo debe tener un buen metodología de como lo va a realizar, las herramientas para mejorar el flujo de trabajo y de comunicación, se utiliza mucho Trello y Slack. Recurso se basa en evitar errores en los trabajos realizados para cumplir la máxima calidad.
>info
>Recordar que ningún producto va a estar 100% libre de errores. Ya que la mayoría de casos se da por no comprender correctamente cómo funciona el producto.

Para ello, la calidad debe ser un compromiso y ética que entregamos algo que funciona, hay que revisar 2 tipos de calidad.
- calidad del producto: se basa en que todo funcione correctamente desde requerimientos, diseño, código y el sistema.
- calidad del proceso: se basa en como lo debe realizar las personas, éstandares, procedimientos y procesos del proyecto.

## 7 Principios del testing moderno
La calidad del producto es responsabilidad de todo el equipo y van a aprender de forma iterativa no hay atajos.
1. Prioridad mejorar el negocio: Entregar valor si ese producto realmente va a hacer funcionar al negocio tenemos que identificar riesgos tempranos y comunicarlo, la mayoría pide que se le integre IA pero algunos no necesitan.
2. Nosotros aceleramos al equipo: Utilizamos Lean Thinking y Teoría de las Restricciones identificando cuellos de botella, he visto que muchos se demoran en Daily Scrum cuando se reunen toma más de 30 minutos en vez de 5 y se desbian hacia otra cosa.
3. Mejora continua: Adaptarse a veces desde el inicio hasta el final vas a llevar testing, puedes adaptarlo por fases.
4. Nos procupamos por la cultura de calidad: Nos volvemos como un Coach versatil entender todas las áreas donde dominamos desarrollo, documentación técnica, lideramos al equipo para llevarlo a una calidad más madura. Acompañar en todo el proceso así como un Scrum master.
5. Nosotros creemos que el cliente es el único que puede juzgar y evaluar: Si el cliente al recibir su software funciona como el espeara haz alcanzado cierta calidad.
6. Nosotros usamos datos de manera extensa y profunda para entender los casos de uso del cliente, es decir nos apoyamos de datos reales para cerrar la brecha contra la experiencia por si alguna vez va a crecer tu aplicación hacia otros países.
7. Expandimos las habilidades de testing y el conocimiento en todo el equipo: No se trata de eliminar al tester, es una habilidad compartida cuando todo el equipo testea el producto mejora.
## Pruebas de caja negra, blanca o gris
![[assets/image.png]]
- Caja Negra: Se prueba la interfaz sin conocer el código. La forma en lo que utiliza el usuario.
- Caja Blanca: Se analiza el código interno (como una caja de cristal) para asegurar cobertura y eliminar riesgos.
- Caja Gris: Se enfoca en la integración, el flujo de datos y los servicios entre el frontend y el backend.

Supongamos un ejemplo tenemos que rellenar un formulario como cliente.

### Técnicas de Caja Negra
- Partición de equivalencia: Agrupar datos en conjuntos válidos e inválidos. Ejemplo, solamente se puede poner el precio hasta 2 decimales
- Valores límite: Probar los extremos de los rangos permitidos. Ejemplo, hasta que punto me deja introducir el decimal que pasara si pongo 1000.999999999
- Tablas de decisiones: Validar combinaciones de opciones fijas (checkboxes/radio buttons). Ejemplos, son selecionables fijos verdadero o falso.
- Transición de estados: Evaluar el comportamiento del componente según su estado. Ejemplo, despues de llenar los otros campos se activan.
- Casos de uso: Verificar flujos completos de interacción del usuario. Ejemplo, verifico que el usuario pueda enviar el formulario y todos los casos son obligatorios.
### Enfoques de Caja Blanca y Gris
La idea es evitar problemas de seguridad se inyecte código malicioso.
- Caja Blanca: Se centra en la cobertura de declaraciones (ejecutar cada línea de código al menos una vez) para garantizar calidad y seguridad.
- Caja Gris: Incluye casos de negocio (Flujo desde el frontend hasta el backend), pruebas end-to-end (flujo donde se procesa los datos en otro lado ya que yo no se que es lo que espero) e integración (comunicación entre servicios estado 201 creado). Ejemplo, el usuario puede compras y ver el estado de su pedido.
- 