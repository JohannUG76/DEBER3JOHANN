package application;

import javafx.application.Application; import javafx.geometry.Insets; import javafx.scene.Scene; import javafx.scene.control.; import javafx.scene.layout.; import javafx.scene.paint.Color; import javafx.stage.Stage;

public class Main extends Application { @Override public void start(Stage primaryStage) { try { // Crear los elementos Label dateLabel = new Label("SELECCIONA UNA FECHA EN EL CALENDARIO"); dateLabel.setTextFill(Color.WHITE); DatePicker datePicker = new DatePicker();

        Label colorLabel = new Label("SELECCIONA UN COLOR");
        colorLabel.setTextFill(Color.WHITE);
        ColorPicker colorPicker = new ColorPicker();

        Button button = new Button("CONFIRMA");
        Label resultLabel = new Label();
        resultLabel.setTextFill(Color.WHITE);

        // Acción al presionar el botón
        button.setOnAction(e -> {
            String selectedDate = datePicker.getValue().toString();
            Color selectedColor = colorPicker.getValue();
            resultLabel.setText("FECHA SELECCIONADA: " + selectedDate + "\nCOLOR SELECCIONADO: " + selectedColor);
            System.out.println("FECHA SELCCIONADA: " + selectedDate);
            System.out.println("COLOR SELECCIONADO: " + selectedColor);
        });

        // Crear el VBox y agregar los elementos
        VBox vbox = new VBox(10, dateLabel, datePicker, colorLabel, colorPicker, button, resultLabel);
        vbox.setSpacing(10);
        vbox.setPadding(new Insets(20));
        vbox.setAlignment(javafx.geometry.Pos.CENTER);

        // Crear un Background con color negro
        BackgroundFill backgroundFill = new BackgroundFill(Color.BLACK, CornerRadii.EMPTY, Insets.EMPTY);
        Background background = new Background(backgroundFill);
        vbox.setBackground(background);

        // Crear la escena
        Scene scene = new Scene(vbox, 450, 300);

        // Configurar el Stage
        primaryStage.setScene(scene);
        primaryStage.setTitle("FECHA Y COLOR");
        primaryStage.show();
    } catch (Exception e) {
        e.printStackTrace();
    }
}

public static void main(String[] args) {
    launch(args);
}
}
![Captura de pantalla 2024-06-11 203848](https://github.com/JohannUG76/DEBER3JOHANN/assets/169223501/6c0287c5-9665-4de2-8059-c60e773f7874)
