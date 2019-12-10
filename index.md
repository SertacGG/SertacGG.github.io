## Welcome to GitHub Pages

Bu hesap denemedir [Aktif Github hesabım](https://github.com/sertacguler) 


package com.datasel.patient;

import javax.swing.*;
import javax.xml.bind.*;

import java.awt.Component;
import java.awt.GridBagLayout;
import java.awt.GridBagConstraints;
import java.awt.Insets;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.MouseAdapter;
import java.awt.event.MouseEvent;
import java.io.ByteArrayOutputStream;
import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.ObjectInputStream;
import java.io.ObjectOutputStream;
import java.io.OutputStreamWriter;
import java.io.Writer;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.ArrayList;

import javax.swing.JTable;
import javax.swing.filechooser.FileNameExtensionFilter;
import javax.swing.filechooser.FileSystemView;
import javax.swing.table.TableCellRenderer;

import com.datasel.entity.Patient;
import com.datasel.entity.Patients;
import com.datasel.repo.Datas;
import com.fasterxml.jackson.core.JsonProcessingException;
import com.fasterxml.jackson.databind.ObjectMapper;

import javax.swing.JScrollPane;

public class PatientMainPanel extends JPanel {

	private static final long serialVersionUID = 1L;
	private final JButton btnAdd = new JButton("ADD");
	private final JButton btnEdt = new JButton("EDIT");
	private final JButton btnDelete = new JButton("DELETE");
	private final JButton btnExport = new JButton("EXPORT");
	private final JButton btnImport = new JButton("IMPORT");
	private final PatientTableModel tableModel = new PatientTableModel();
	private final JTable table = new JTable();
	private final JScrollPane scrollPane = new JScrollPane();

	private ArrayList<String> selectedIdList = new ArrayList<String>();
	private ArrayList<Patient> patients_head = new ArrayList<Patient>();
	private String path;
	private String type;
	private String patients_type = "";

	public PatientMainPanel() {

		GridBagLayout gridBagLayout = new GridBagLayout();
		gridBagLayout.columnWidths = new int[] { 0, 0, 0, 0, 0, 0, 0, 5, 0 };
		gridBagLayout.rowHeights = new int[] { 5, 0, 0, 0, 0 };
		gridBagLayout.columnWeights = new double[] { 0.0, 1.0, 0.0, 0.0, 0.0,
				0.0, 0.0, 0.0, Double.MIN_VALUE };
		gridBagLayout.rowWeights = new double[] { 0.0, 0.0, 1.0, 0.0,
				Double.MIN_VALUE };
		setLayout(gridBagLayout);

		GridBagConstraints gbc_btnImport = new GridBagConstraints();
		gbc_btnImport.insets = new Insets(0, 0, 5, 5);
		gbc_btnImport.gridx = 2;
		gbc_btnImport.gridy = 1;
		add(btnImport, gbc_btnImport);

		GridBagConstraints gbc_btnExport = new GridBagConstraints();
		gbc_btnExport.insets = new Insets(0, 0, 5, 5);
		gbc_btnExport.gridx = 3;
		gbc_btnExport.gridy = 1;
		add(btnExport, gbc_btnExport);

		GridBagConstraints gbc_btnAdd = new GridBagConstraints();
		gbc_btnAdd.insets = new Insets(0, 0, 5, 5);
		gbc_btnAdd.gridx = 4;
		gbc_btnAdd.gridy = 1;
		add(btnAdd, gbc_btnAdd);

		GridBagConstraints gbc_btnEdt = new GridBagConstraints();
		gbc_btnEdt.insets = new Insets(0, 0, 5, 5);
		gbc_btnEdt.gridx = 5;
		gbc_btnEdt.gridy = 1;
		add(btnEdt, gbc_btnEdt);

		GridBagConstraints gbc_btnDelete = new GridBagConstraints();
		gbc_btnDelete.insets = new Insets(0, 0, 5, 5);
		gbc_btnDelete.gridx = 6;
		gbc_btnDelete.gridy = 1;
		add(btnDelete, gbc_btnDelete);

		GenerealEventListener eventListener = new GenerealEventListener(this);
		btnAdd.setActionCommand("ADD");
		btnEdt.setActionCommand("EDIT");
		btnDelete.setActionCommand("DELETE");
		btnExport.setActionCommand("EXPORT");
		btnImport.setActionCommand("IMPORT");

		GridBagConstraints gbc_scrollPane = new GridBagConstraints();
		gbc_scrollPane.gridwidth = 6;
		gbc_scrollPane.insets = new Insets(0, 0, 5, 5);
		gbc_scrollPane.fill = GridBagConstraints.BOTH;
		gbc_scrollPane.gridx = 1;
		gbc_scrollPane.gridy = 2;
		add(scrollPane, gbc_scrollPane);
		scrollPane.setViewportView(table);

		table.setModel(tableModel);

		table.setRowHeight(70);

		Datas datas = new Datas();
		patients_head = datas.databaseConn();

		// image
		table.getColumnModel().getColumn(5)
				.setCellRenderer(new Renderer(patients_head));
		// checkbox cell
		table.getColumnModel().getColumn(0)
				.setCellRenderer(new Renderer(patients_head));
		table.setPreferredScrollableViewportSize(table.getPreferredSize());

		// color
		for (int i = 0; i < tableModel.getColumnCount(); i++) {
			table.setDefaultRenderer(table.getColumnClass(i),
					new WineCellRenderer());
		}

		btnAdd.addActionListener(eventListener);
		btnEdt.addActionListener(eventListener);
		btnDelete.addActionListener(eventListener);
		btnExport.addActionListener(eventListener);
		btnImport.addActionListener(eventListener);

		tableModel.setPatients(patients_head);
		tableModel.fireTableDataChanged();

		table.addMouseListener(new MouseAdapter() {
			public void mouseClicked(MouseEvent e) {
				boolean selected = tableModel.getPatients()
						.get(table.getSelectedRow()).isSelected();
				int x = 0;
				if (e.getClickCount() % 2 == 1) {
					selected = (selected == true) ? false : true;
					if (selected == true) {
						selectedIdList.add(String.valueOf(tableModel
								.getPatients().get(table.getSelectedRow())
								.getPatient_id()));
					} else {
						x = selectedIdList.indexOf(String.valueOf(tableModel
								.getPatients().get(table.getSelectedRow())
								.getPatient_id()));
						selectedIdList.remove(x);
					}
				}
				// System.out.println(idList);
				tableModel.getPatients().get(table.getSelectedRow())
						.setSelected(selected);

				tableModel.fireTableDataChanged();
			}
		});

	}

	public class Renderer implements TableCellRenderer {
		JCheckBox c = new JCheckBox();
		ArrayList<Patient> patients1 = new ArrayList<Patient>();

		public Renderer(ArrayList<Patient> patients) {
			this.patients1 = patients;
		}

		@Override
		public Component getTableCellRendererComponent(JTable table,
				Object data, boolean isSelected, boolean hasFocus, int row,
				int column) {
			if (column == 5) {
				JLabel label = new JLabel();
				label.setIcon((ImageIcon) data);
				return label;
			} else {
				c.setSelected(patients1.get(row).isSelected());
				return c;
			}
		}
	}

	class GenerealEventListener implements ActionListener {
		private JPanel panel;

		public GenerealEventListener(JPanel panel) {
			this.panel = panel;
		}

		@Override
		public void actionPerformed(ActionEvent e) {
			String cmd = e.getActionCommand();
			Patient patient = null;
			if (cmd.equals("ADD")) {
				addBtnAction(patient);
			} else if (cmd.equals("EDIT")) {
				editBtnAction(patient);
			} else if (cmd.equals("DELETE")) {
				deleteBtnAction();
			} else if (cmd.equals("EXPORT")) {
				exportBtnAction();
			} else if (cmd.equals("IMPORT")) {
				importBtnAction();
			}
		}

		private void addBtnAction(Patient patient) {
			patient = openEditor(patient);
			if (patient != null) {
				Datas datas = new Datas();
				datas.databaseAdd(patient);
				tableModel.getPatients().add(patient);
				tableModel.fireTableDataChanged();
			}
		}

		private void editBtnAction(Patient patient) {
			Datas datas = new Datas();
			if (selectedIdList.size() == 0) {
				JOptionPane.showMessageDialog(null, "Not Selected", "Hey!",
						JOptionPane.ERROR_MESSAGE);
			} else if (selectedIdList.size() < 2) {
				for (int i = 0; i < patients_head.size(); i++) {
					if (patients_head.get(i).getPatient_id() == Integer
							.valueOf(selectedIdList.get(0))) {
						patient = patients_head.get(i);
					}
				}
				patient = openEditor(patient);
				datas.databaseEdit(patient);
				selectedIdList.clear();
				tableModel.setPatients(datas.databaseConn());
				tableModel.fireTableDataChanged();
			} else {
				JOptionPane.showMessageDialog(null,
						"You can choose only 1 patient", "Hey!",
						JOptionPane.ERROR_MESSAGE);
			}
		}

		private void deleteBtnAction() {
			Datas datas = new Datas();
			if (selectedIdList.size() != 0) {
				int input = JOptionPane.showConfirmDialog(null,
						"Are you sure?", "Delete", JOptionPane.YES_NO_OPTION);
				if (input == 0) {
					for (int i = 0; i < selectedIdList.size(); i++) {
						datas.databaseDelete(Integer.valueOf(selectedIdList
								.get(i)));
						tableModel.getPatients().remove(ar(i));
					}
					selectedIdList.clear();
					tableModel.fireTableDataChanged();
				}
			} else {
				JOptionPane.showMessageDialog(null, "Not Selected", "Hey!",
						JOptionPane.ERROR_MESSAGE);
			}
		}

		private void exportBtnAction() throws JAXBException, IOException {
			jChooser();
			if (type.contains("xml")) {
				for (Patient patient : patients_head) {
					if (patient.isSelected()) {
						patients_type = writePatientXML(patient);
						fileSave(patient, patients_type);
					}
				}
			}
			/*
			 * if (type.contains("xml")) { for (int i = 0; i <
			 * selectedIdList.size(); i++) { for (int x = 0; x <
			 * patients_head.size(); x++) { if
			 * (patients_head.get(x).getPatient_id() == Integer
			 * .valueOf(selectedIdList.get(i))) { try { } catch (IOException |
			 * JAXBException e1) { e1.printStackTrace(); }
			 * fileSave(patients_head.get(x)); } } } } else if
			 * (type.contains("json")) { for (int i = 0; i <
			 * selectedIdList.size(); i++) { for (int x = 0; x <
			 * patients_head.size(); x++) { if
			 * (patients_head.get(x).getPatient_id() == Integer
			 * .valueOf(selectedIdList.get(i))) { patients_type =
			 * writePatientJSON(patients_head .get(x));
			 * fileSave(patients_head.get(x)); } } } }
			 */
			else if (type.contains("jo")) {
				for (int i = 0; i < selectedIdList.size(); i++) {
					for (int x = 0; x < patients_head.size(); x++) {
						if (patients_head.get(x).getPatient_id() == Integer
								.valueOf(selectedIdList.get(i))) {
							writePatientJO(patients_head.get(x));
						}
					}
				}
			}
			patients_type = "";
			selectedIdList.clear();
		}

		private void importBtnAction() {
			Patient patient = new Patient();
			String pathX = jChooserImport();
			try {
				patient = readPatientJO(pathX);
			} catch (ClassNotFoundException e1) {
				e1.printStackTrace();
			}
			Datas datas = new Datas();
			datas.databaseAdd(patient);
			tableModel.getPatients().add(patient);
			tableModel.fireTableDataChanged();
			// System.out.println(patient);
		}

		private void jChooser() {
			JFileChooser jfc = new JFileChooser(FileSystemView
					.getFileSystemView().getHomeDirectory());
			jfc.setDialogTitle("Name");
			jfc.setAcceptAllFileFilterUsed(false);
			FileNameExtensionFilter filter = new FileNameExtensionFilter("XML",
					".xml");
			FileNameExtensionFilter filter1 = new FileNameExtensionFilter(
					"JSON", ".json");
			FileNameExtensionFilter filter2 = new FileNameExtensionFilter(
					"Java Object", ".jo");
			jfc.addChoosableFileFilter(filter);
			jfc.addChoosableFileFilter(filter1);
			jfc.addChoosableFileFilter(filter2);
			jfc.setFileFilter(filter);
			jfc.setFileFilter(filter1);
			jfc.setFileFilter(filter2);
			int returnValue = jfc.showOpenDialog(null);

			if (returnValue == JFileChooser.APPROVE_OPTION) {
				path = jfc.getCurrentDirectory().toString();
				System.out.println(path);
				System.out.println(path);
				if (jfc.getFileFilter().getDescription().equals("XML")) {
					type = ".xml";
				} else if (jfc.getFileFilter().getDescription().equals("JSON")) {
					type = ".json";
				} else if (jfc.getFileFilter().getDescription()
						.equals("Java Object")) {
					type = ".jo";
				}
			}
		}

		private String jChooserImport() {
			JFileChooser fileChooser = new JFileChooser();
			fileChooser.setCurrentDirectory(new File(System
					.getProperty("user.home")));
			fileChooser.setFileSelectionMode(JFileChooser.FILES_ONLY);

			fileChooser.addChoosableFileFilter(new FileNameExtensionFilter(
					"Java Object", ".jo"));
			fileChooser.setAcceptAllFileFilterUsed(true);
			File selectedFile = null;
			int result = fileChooser.showOpenDialog(null);
			if (result == JFileChooser.APPROVE_OPTION) {
				selectedFile = fileChooser.getSelectedFile();
			}
			return selectedFile.getAbsolutePath().toString();
		}

		public Patient readPatientJO(String pathX)
				throws ClassNotFoundException {
			ObjectInputStream ois = null;
			FileInputStream fis;
			Patient patient = new Patient();
			try {
				fis = new FileInputStream(pathX);
				ois = new ObjectInputStream(fis);
				patient = (Patient) ois.readObject();
				ois.close();
			} catch (FileNotFoundException e) {
				e.printStackTrace();
			} catch (IOException e) {
				e.printStackTrace();
			}
			return patient;
		}

		public void writePatientJO(Patient patient) {
			FileOutputStream fout = null;
			ObjectOutputStream oos = null;
			String pathX = "";
			try {
				pathX = path + "\\_patient_" + patient.getPatient_id()
						+ patient.getName() + type;
				System.out.println("path : " + pathX);
				fout = new FileOutputStream(pathX);
				oos = new ObjectOutputStream(fout);
				oos.writeObject(patient);

			} catch (Exception ex) {
				ex.printStackTrace();
			} finally {
				if (fout != null) {
					try {
						fout.close();
					} catch (IOException e) {
						e.printStackTrace();
					}
				}
				if (oos != null) {
					try {
						oos.close();
					} catch (IOException e) {
						e.printStackTrace();
					}
				}
				pathX = "";
			}
		}

		private String writePatientJSON(Patient patient) {
			ObjectMapper Obj = new ObjectMapper();
			try {
				patients_type = Obj.writeValueAsString(patient);
			} catch (JsonProcessingException e1) {
				e1.printStackTrace();
			}
			return patients_type;
		}

		private String writePatientXML(Patient patient) throws JAXBException,
				IOException {
			Patients patientsXml = new Patients();
			// patientsXml.getPatient().addAll(selectedFindArray());
			// XML dosyasina birden fazla kaydetmek istediginde
			patientsXml.getPatient().add(patient);

			JAXBContext jaxbContext = JAXBContext.newInstance(Patients.class);
			Marshaller jaxbMarshaller = jaxbContext.createMarshaller();
			jaxbMarshaller.setProperty(Marshaller.JAXB_FORMATTED_OUTPUT, true);
			jaxbMarshaller.setProperty(Marshaller.JAXB_ENCODING, "UTF-8");
			ByteArrayOutputStream out = new ByteArrayOutputStream();
			Writer w = new OutputStreamWriter(out, "UTF-8");

			jaxbMarshaller.marshal(patientsXml, w);
			w.flush();
			byte[] bytes = out.toByteArray();
			String xml = new String(bytes, "UTF-8");
			return xml.toString();
		}

		private void fileSave(Patient patient, String patients_type) {

			String pathX = "";
			pathX = path + "\\_patient_" + patient.getPatient_id()
					+ patient.getName() + type;
			System.out.println("path : " + pathX);

			try {
				Files.write(Paths.get(pathX), patients_type.getBytes());

			} catch (FileNotFoundException e1) {
				e1.printStackTrace();
			} catch (IOException e1) {
				e1.printStackTrace();
			}
			pathX = "";
		}

		public int ar(int x) {
			int a = 0;
			for (int i = 0; i < patients_head.size(); i++) {
				if (patients_head.get(i).getPatient_id() == Integer
						.valueOf(selectedIdList.get(x))) {
					a = i;
				}
			}
			return a;
		}

		private Patient openEditor(Patient patient) {
			JDialog dialog = new JDialog(
					JOptionPane.getFrameForComponent(panel), "Create Patient",
					true);
			PatientEditor patientEditor = new PatientEditor(patient);
			patientEditor.setDialog(dialog);
			dialog.getContentPane().add(patientEditor);
			dialog.setLocationByPlatform(true);
			dialog.setSize(600, 250);
			dialog.setVisible(true);
			patient = patientEditor.getPatient();
			return patient;
		}

	}
}
