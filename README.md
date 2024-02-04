public class MathUtils {

    public int add(int a, int b) {
        return a + b;
    }

    public int subtract(int a, int b) {
        return a - b;
    }

    public int multiply(int a, int b) {
        return a * b;
    }

    public double divide(int a, int b) {
        if (b != 0) {
            return (double) a / b;
        } else {
            System.out.println("Error: Division by zero is not allowed.");
            return -1.0; // Handle division by zero by returning -1.0
        }
    }
}
import org.junit.After;
import org.junit.Before;
import org.junit.Test;
import static org.junit.Assert.*;

public class MathUtilsTest {

    private MathUtils mathUtils;

    @Before
    public void setUp() {
        mathUtils = new MathUtils();
    }

    @Test
    public void testAdd() {
        assertEquals(5, mathUtils.add(2, 3));
        assertEquals(-1, mathUtils.add(-4, 3));
        assertEquals(0, mathUtils.add(0, 0));
    }

    @Test
    public void testSubtract() {
        assertEquals(2, mathUtils.subtract(5, 3));
        assertEquals(-7, mathUtils.subtract(0, 7));
        assertEquals(0, mathUtils.subtract(10, 10));
    }

    @Test
    public void testMultiply() {
        assertEquals(15, mathUtils.multiply(3, 5));
        assertEquals(0, mathUtils.multiply(0, 7));
        assertEquals(-12, mathUtils.multiply(4, -3));
    }

    @Test
    public void testDivide() {
        assertEquals(2.5, mathUtils.divide(5, 2), 0.0001);
        assertEquals(-3.0, mathUtils.divide(9, -3), 0.0001);
        assertEquals(-1.0, mathUtils.divide(0, 0), 0.0001); // Division by zero returns -1.0
    }

    @After
    public void tearDown() {
        mathUtils = null;
    }
}
