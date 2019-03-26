# ArrayList

## Arrays.asList UnsupportedOperationException

- Arrays.asList는 fixed size로 arraylist를 리턴함, 그래서 addAll or add를 할 경우 ***UnsupportedOperationException*** 가 발생함

```
	@Test(expected = UnsupportedOperationException.class)
	public void occurException() {
		List<String> testList = Arrays.asList("T1", "T2"); //'Arrays.asList' a fixed sized list

		testList.add("T3");
	}

	@Test
	public void ok_1() {
		List<String> testList = new ArrayList<>(Arrays.asList("T1", "T2"));
		testList.add("T3");
		testList.addAll(Arrays.asList("T4", "T5"));

		Assert.assertEquals(5, testList.size());
	}

	@Test
	public void ok_2() {
		List<String> testList = new ArrayList<>(Arrays.asList("T1", "T2"));
		testList.add("T3");
		testList.addAll(Arrays.asList("T4", "T5"));

		Assert.assertEquals(5, testList.size());

		Collections.addAll(testList, "T7", "T8");
		Assert.assertEquals(7, testList.size());
	}

```