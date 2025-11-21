```java
/* Not the most efficient solution, I wrote this myself without referencing, but hey it works */

public static String rot13(String e) {
	StringBuilder ds = new StringBuilder();  // holds decoded string
	
	for (int c : e.toCharArray()) {
		if (c >= 65 && c <= 90) {  // upper case
			c += 13;
			if (c > 90)
				c = 65 + (c - 90 - 1);
		}
		else if (c >= 97 && c <= 122) {  // lower case
			c += 13;
			if (c > 122)
				c = 97 + (c - 122 - 1);
		}
		ds.append((char) c);
	}
	
	return ds.toString();
}
```