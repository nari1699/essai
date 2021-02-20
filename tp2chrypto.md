# essai
premier essai repository
Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package tpcrypto;
import java.security.*;
import javax.crypto.*;
import java.security.NoSuchAlgorithmException;
import java.util.Random;

/**
 *
 * @author hp
 */
public class TPcrypto {

    /**
     * @param args the command line arguments
     */
    //LA FONCTION QUI CONVERTIE UN HEXADECIMAL EN DECIMAL
       public static int decimal(String nb)
       {
           String hexd;
           int m,num=0;
           char lett;
           hexd="0123456789ABCDEF";
           nb=nb.toUpperCase();
           num=0;
           for(int i=0;i<nb.length();i++)
           {
               lett=nb.charAt(i);
               m=hexd.indexOf(lett);
               num=16*num+m;
           }
           return num;
       }
    public static void main(String[] args) throws NoSuchAlgorithmException {
        // TODO code application logic here

         //VERIFFICATION QUE DECIMAL MARCHE
       //System.out.println(decimal("A"));
       
       Random rand= new Random();
       
       String id="zahafiyasminenarimene";
       String x;
     
      
       double i;
       double count=0;
       
      /*for (i=0;sha1(id+rand.nextInt())<"03B1663DDA6549A0939FFDD712A852E0D4234E6B";i++)
      {
          count=i; 
      }*/
        //System.out.println(decimal("03B1663DDA6549A0939FFDD712A852E0D4234E6B"));
        System.out.println("le resultat de SH1 (id||x):");
        System.out.println(sha1(id+rand.nextInt()));
        System.out.println(" X est egal à:");
        System.out.println(rand.nextInt());
        System.out.println("le nombre d'iteration pour trouver le X est egal à");
        System.out.println(count);
    }
     static String sha1(String input) throws NoSuchAlgorithmException {
        MessageDigest mDigest = MessageDigest.getInstance("SHA1");
        byte[] result = mDigest.digest(input.getBytes());
        StringBuffer sb = new StringBuffer();
        for (int i = 0; i < result.length; i++) {
            sb.append(Integer.toString((result[i] & 0xff) + 0x100, 16).substring(1));
        }
         
        return sb.toString();
    }

    private static int sh1(String chaine) {
        throw new UnsupportedOperationException("Not supported yet."); //To change body of generated methods, choose Tools | Templates.
    }
}
