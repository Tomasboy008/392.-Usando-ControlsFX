# 392.-Usando-ControlsFX
caixa de login completa
INICIO
_________________________

public class LoginControlador {

	@FXML
	private TextField campoEmail;
	
	@FXML
	private PasswordField campoSenha;

	public void entrar() {
		boolean emailValido = campoEmail.getText().equals("aluno@cod3r.com.br");
		boolean senhaValida = campoSenha.getText().equals("12345678");
		
		if(emailValido && senhaValida) {
			Notifications.create()
			              .position(Pos.TOP_CENTER)
						  .title("Loguin FXML")
						  .text("Login efetuado com sucesso!")
						  .showInformation();
		} else
			Notifications.create()
						  .position(Pos.TOP_CENTER)
			  			  .title("Loguin FXML")
			              .text("Usuário ou senha invalidos!")
			              .showError();
	}
}
______________________________________________
public class AppFXML extends Application {
	
	@Override
	public void start(Stage primaryStage) throws Exception {
		String arquivoCSS = getClass().getResource("/fxml/Login.css").toExternalForm();
		URL arquivoFXML = getClass().getResource("/fxml/Login.fxml");
		GridPane raiz = FXMLLoader.load(arquivoFXML);
		
		Scene cena = new Scene(raiz, 350, 350);
		cena.getStylesheets().add(arquivoCSS);
		
		primaryStage.setResizable(false);
		primaryStage.setTitle("Tela de Login");
		primaryStage.setScene(cena);
		primaryStage.show();
	}
	public static void main(String [] args) {
		launch(args);
	}
}
_____________________________________________
module exerciciosfx {
	requires javafx.controls;
	requires javafx.fxml;
	requires org.controlsfx.controls;
	opens basico;
	opens layout;
	opens fxml;
}
___________________________________________
ARQUIVO FXML USADO:
GridPane
  padding
  columnConstraints
  Label
  TextField
  PasswordField
  Button
  GridPane.margin
  ____________________________________________
  ![image](https://user-images.githubusercontent.com/95525963/153756553-16ca30c1-9540-4b4a-8032-59f95e7e74fd.png)

