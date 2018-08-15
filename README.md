# HelloCaiCai
Learning makes me happy！
##Learning notes


package chap13;

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class Excese3 extends JFrame{
	public Excese3() {
		setBounds(10,10,500,500);
		Container c  = getContentPane();
		c.setLayout(new BorderLayout());
		JLabel label1 = new JLabel("用户名：");
		JLabel label2 = new JLabel("密码：");
		JTextField textfield1 = new JTextField();
		JPasswordField passwordfield = new JPasswordField();
		//JTextField textfield2 = new JTextField();
		JPanel panel1 = new JPanel();
		JPanel panel2 = new JPanel();
		panel1.setLayout(new GridLayout(2, 2));
		panel1.add(label1);panel1.add(textfield1);panel1.add(label2);panel1.add(passwordfield);
		c.add(panel1,BorderLayout.NORTH);
		JButton b1 = new JButton("提交");
		JButton b2 = new JButton("重置");
		panel2.add(b1);panel2.add(b2);
		c.add(panel2,BorderLayout.SOUTH);
		
		//trim()去掉字符串首尾的空格
		b1.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				if(textfield1.getText().trim().length()==0||new String(passwordfield.getPassword()).trim().length()==0){
					JOptionPane.showMessageDialog(null, "用户名或密码不能为空");
					return;//方法结束
				}
				if(textfield1.getText().trim().equals("mr")&&new String(passwordfield.getPassword()).trim().equals("mrsoft")) {
					JOptionPane.showMessageDialog(null, "登陆成功！");
				}
				else{
					JOptionPane.showMessageDialog(null, "用户名或密码错误，请重新输入");
					textfield1.setText("");passwordfield.setText("");
				}
			}
		});
		b2.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				textfield1.setText("");passwordfield.setText("");
			}
		});
		
		
		setVisible(true);
  	    setDefaultCloseOperation(EXIT_ON_CLOSE);
	}
public static void main(String[] args) {
	new Excese3();
}
}
