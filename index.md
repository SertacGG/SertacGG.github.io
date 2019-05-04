## Welcome to GitHub Pages

Bu hesap denemedir [Aktif Github hesabım](https://github.com/sertacguler) 

DataView.java
import javax.annotation.PostConstruct;
import javax.faces.bean.ManagedBean;
import javax.faces.bean.ViewScoped;
import java.util.ArrayList;
import java.util.List;

@ManagedBean
@ViewScoped
public class DataVİew {

    private List<Student> stundets = new ArrayList<Student>();

    @PostConstruct
    public void init() {

        stundets.add(new Student("Sertac", "Guler", 21, "12345"));
        stundets.add(new Student("Burak", "Yılmaz", 20, "12346"));
        stundets.add(new Student("Muhmut", "Tuncer", 22, "12347"));
        stundets.add(new Student("Onur", "Öztürk", 23, "12348"));
        
    }

    public List<Student> getStundets() {
        return stundets;
    }

}

Student.java
public class Student {

    private String name;
    private String surname;
    private int age;
    private String tc_no;

    public Student() {
    }

    public Student(String name, String surname, int age, String tc_no) {
        this.name = name;
        this.surname = surname;
        this.age = age;
        this.tc_no = tc_no;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getSurname() {
        return surname;
    }

    public void setSurname(String surname) {
        this.surname = surname;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public String getTc_no() {
        return tc_no;
    }

    public void setTc_no(String tc_no) {
        this.tc_no = tc_no;
    }
}


dataview.xhtml
<ui:composition version="1.0"
                encoding="UTF-8"
                template="template.xhtml"
                xmlns="http://www.w3.org/1999/xhtml"
                xmlns:h="http://xmlns.jcp.org/jsf/html"
                xmlns:ui="http://xmlns.jcp.org/jsf/facelets"
                xmlns:f="http://xmlns.jcp.org/jsf/core"
                xmlns:p="http://primefaces.org/ui">

    <ui:define name="content">

        <h:head>
            <title>AnaSayfa</title>
        </h:head>
        <h:body>

            <h1>Data View</h1>
            <p:dataTable var="student" value="#{dataVİew.stundets}">
                <p:column headerText="Name">
                    <h:outputText value="#{student.name}"/>
                </p:column>

                <p:column headerText="Surname">
                    <h:outputText value="#{student.surname}"/>
                </p:column>

                <p:column headerText="Age">
                    <h:outputText value="#{student.age}"/>
                </p:column>

                <p:column headerText="Tc No">
                    <h:outputText value="#{student.tc_no}"/>
                </p:column>
            </p:dataTable>

        </h:body>

    </ui:define>

</ui:composition>



top.xhtml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
        "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml"
      xmlns:h="http://xmlns.jcp.org/jsf/html"
      xmlns:ui="http://xmlns.jcp.org/jsf/facelets"
      xmlns:f="http://xmlns.jcp.org/jsf/core"
      xmlns:p="http://primefaces.org/ui">

<ui:composition>

    <h:form>

        <p:tabMenu activeIndex="0">
            <p:menuitem value="Ana Sayfa" action="index" icon="pi pi-star">
                <f:param name="i" value="0"/>
            </p:menuitem>
            <p:menuitem value="DataView" action="dataview" icon="pi pi-search">
                <f:param name="i" value="1"/>
            </p:menuitem>
            <p:menuitem value="Logout" action="#{loginJsf.log_out}" icon="pi pi-file">
                <f:param name="i" value="2"/>
            </p:menuitem>
        </p:tabMenu>

    </h:form>

</ui:composition>
</html>


