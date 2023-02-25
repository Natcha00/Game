
import java.awt.Dimension;
import javax.swing.ImageIcon;
import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.JLabel;
import java.awt.FlowLayout;
import java.util.ArrayList;

public class Window extends JPanel {
    private JFrame f;
    private JLabel logoIcon;
    private ImageIcon icon;

    Window() {
        f = new JFrame("FYB");
        f.setSize(1000, 1000);
        f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        Image("burgur");
        f.setVisible(true);
    }

    public void Image(String action) {
        ArrayList<PopupImage> popupImageList = new ArrayList<>();
        popupImageList.add(new PopupImage("img/pizza.png", "pizza"));
        popupImageList.add(new PopupImage("img/burgur.png", "burgur"));

        String tempImage = "img/Logo.png";

        for (PopupImage popupImage : popupImageList) {
            if (popupImage.getAction().equals(action)) {
                tempImage = popupImage.getImageName();
            }
        }

        icon = new ImageIcon(tempImage);
        logoIcon = new JLabel(icon);
        logoIcon.setPreferredSize(new Dimension(510, 510));
        f.add(logoIcon);
    }

