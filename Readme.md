	String intToBin(int n) {
		return intToBinaryWithSeparator(n, " , ");
	}
int n=68;
byte b=127;
char c='B';
b=(byte)'n';
	String intToBinaryWithSeparator(int n, String separator) {
		String str = String.format("%032d", new java.math.BigInteger(Integer.toBinaryString(n)));

		String[] as = str.split("(?<=\\G........)");

		java.util.stream.Stream<String> streamIn = java.util.Arrays.stream(as);

		java.util.stream.Stream<String> streamOut = streamIn.map(s -> {
			java.lang.StringBuilder sb = new java.lang.StringBuilder(s);
			sb.insert(4, '_');
			return sb.toString();
		});
"errors fixed"
int n=68;
byte b=127;
char c='B';
b=(byte)n;
c=(char)n;
		return streamOut.collect(java.util.stream.Collectors.joining(separator));
	}