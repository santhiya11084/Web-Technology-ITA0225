import java.io.IOException;
import java.io.PrintWriter;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

@WebServlet("/EmployeeServlet")
public class EmployeeServlet extends HttpServlet {
    private static final long serialVersionUID = 1L;

    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {

        // Set the response content type to HTML
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();

        // Simple hardcoded employee details
        String[][] employees = {
            {"1", "Alice", "Manager"},
            {"2", "Bob", "Developer"},
            {"3", "Charlie", "Designer"}
        };

        // Start HTML output
        out.println("<html><body>");
        out.println("<h1>Employee Details</h1>");
        out.println("<table border='1' cellpadding='5' cellspacing='0'>");
        out.println("<tr><th>ID</th><th>Name</th><th>Position</th></tr>");

        // Display employee details in the table
        for (String[] employee : employees) {
            out.println("<tr>");
            out.println("<td>" + employee[0] + "</td>");
            out.println("<td>" + employee[1] + "</td>");
            out.println("<td>" + employee[2] + "</td>");
            out.println("</tr>");
        }

        // End HTML output
        out.println("</table>");
        out.println("</body></html>");
    }

    protected void doPost(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        doGet(request, response);
    }
}
<servlet>
    <servlet-name>EmployeeServlet</servlet-name>
    <servlet-class>EmployeeServlet</servlet-class>
</servlet>
<servlet-mapping>
    <servlet-name>EmployeeServlet</servlet-name>
    <url-pattern>/EmployeeServlet</url-pattern>
</servlet-mapping>
