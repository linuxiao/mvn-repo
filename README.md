# Des CBC、RSA加密解密
## 引入到项目中
### Step1:
在工程的build.grade 文件中添加：
```
repositories {
    jcenter()
    maven { url "https://raw.githubusercontent.com/linuxiao/mvn-repo/master/repository" }
}
```
### Step2:
```
dependencies {  
  //cbc加密解密
  compile 'cn.com.fujica:des:1.0'  
  //rsa 加密解密
  complie 'cn.com.fujica:rsa:1.0'
} 
```
## 使用
- FujicaRsaHelper
``` java
/***
 * 私钥分段加密数据，每段之间用@符号连接
 * 
 * @param plainText
 *            要加密的字符串
 * @param key
 *            私钥
 * @return
 */
public static String segmentEncryptDataFromStrByPrivateKey(
		String plainText, String key) ;

/***
 * 私钥加密数据
 * 
 * @param plainText
 *            要加密的字符串
 * @param key
 *            私钥
 * @return
 */
public static String encryptDataFromStrByPrivateKey(String plainText,
		String key) ;

/***
 * 私钥分段解密，每段用@符号连接
 * 
 * @param plainText
 *            分段的密文
 * @param key
 *            私钥
 * @return
 */
public static String segmentDecryptDataFromStrByPrivateKey(
		String plainText, String key) ;

/***
 * 私钥解密
 * 
 * @param plainText
 *            密文
 * @param key
 *            私钥
 * @return
 */
public static String decryptDataFromStrByPrivateKey(String plainText,
		String key) ;

/***
 * 公钥分段加密数据，每段之间用@符号连接
 * 
 * @param plainText
 *            要加密的字符串
 * @param key
 *            公钥
 * @return
 */
public static String segmentEncryptDataFromStrByPublicKey(
		String plainText, String key) ;

/***
 * 公钥加密数据
 * 
 * @param plainText
 *            要加密的字符串
 * @param key
 *            公钥
 * @return
 */
public static String encryptDataFromStrByPublicKey(String plainText,
		String key);

/***
 * 公钥分段解密，每段用@符号连接
 * 
 * @param plainText
 *            分段的密文
 * @param key
 *            公钥
 * @return
 */
public static String segmentDecryptDataFromStrByPublicKey(
		String plainText, String key);

/***
 * 公钥解密
 * 
 * @param plainText
 *            密文
 * @param key
 *            公钥
 * @return
 */
public static String decryptDataFromStrByPublicKey(String plainText,
		String key) ;

private final static int offset = 100;

/***
 * 将数据分割为100个字符的数组
 * 
 * @param s
 *            原始数据
 * @return
 */
public static List<String> rsaString2Array(String s) ;

```
- FujicaDes3Helper
```
 /***
 * CBC解密
 * 
 * @param strKey
 *            key 密钥 String类型
 * @param decodeString
 *            Base64编码的密文
 * @return 明文
 * @throws Exception
 */
public static String des3DecodeCBC(String strKey, String decodeString);

/***
 * CBC加密
 * 
 * @param strKey
 *            key 密钥 String类型
 * @param encodeString
 *            明文
 * @return 密文
 * @throws Exception
 */
public static String des3EncodeCBC(String strKey, String encodeString);
```