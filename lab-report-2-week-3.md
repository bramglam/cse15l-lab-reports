# Part One

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}

  @Test 
	public void testReverseInPlace2() {
    int[] input2 = { 1,3,5,7,9 };
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{ 9,7,5,3,1 }, input2);
	}

  @Test 
	public void testReverseInPlace3() {
    int[] input3 = { 0,2,4,6,8 };
    ArrayExamples.reverseInPlace(input3);
    assertArrayEquals(new int[]{ 8,6,4,2,0 }, input3);
	}


  @Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }

  @Test
  public void testReversed2() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }


  @Test
  public void testAverageWithoutLowest(){
    double[] input1= {2,4,6};
    
    double output= 5;
    assertEquals(output, ArrayExamples.averageWithoutLowest(input1),0);
  }

  @Test
  public void testAverageWithoutLowest2(){
    double[] input1= {2,6,6};
    
    double output= 6;
    assertEquals(output, ArrayExamples.averageWithoutLowest(input1),0);
  }

  @Test
  public void testAverageWithoutLowest3(){
    double[] input1= {2,2,2,2};
    
    double output= 2;
    assertEquals(output, ArrayExamples.averageWithoutLowest(input1),0);
  }

  @Test
  public void testAverageWithoutLowest4(){
    double[] input1= {0,0,0,0};
    
    double output= 0;
    assertEquals(output, ArrayExamples.averageWithoutLowest(input1),0);
  }

  @Test
  public void testAverageWithoutLowest5(){
    double[] input1= {2,2,2,2,2,4,4};
    
    double output= 0;
    assertEquals(output, ArrayExamples.averageWithoutLowest(input1),0);
  }
}

# Part Two
