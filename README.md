using UnityEngine;
using UnityEngine.UI;
using UnityEngine.SceneManagement;
public class ButonGame : MonoBehaviour
{
    public static int money;
    public static int rate = 1;
    public static int Clickrate;
    public Text moneyText;
    public Image image;
    public Image image1;
    public Image image2;
    public Image image3;
    public Image image4;
    public Image image5;
    public Image image6;
    public Image image7;
    public Image image8;
    

    private void Start()
    {

        money = PlayerPrefs.GetInt("money", money);
        rate = PlayerPrefs.GetInt("rate", rate);
        Clickrate = PlayerPrefs.GetInt("Clickrate", Clickrate);
        image.gameObject.SetActive(false);
        image1.gameObject.SetActive(false);
        image2.gameObject.SetActive(false);
        image3.gameObject.SetActive(false);
        image4.gameObject.SetActive(false);
        image5.gameObject.SetActive(false);
        image6.gameObject.SetActive(false); 
        image8.gameObject.SetActive(false);
        
    }

    public void Scenes(int numberScenes)
    {
        SceneManager.LoadScene(numberScenes);
    }
    public void Click()
    {
        money += rate;
        PlayerPrefs.SetInt("money", money);
    }
    public void Upgrade()
    {
        if (money >= 50)
        {
            money -= 50;
            rate += 1;
            Clickrate += 1;
            PlayerPrefs.SetInt("money", money);
            PlayerPrefs.SetInt("rate", rate);
            PlayerPrefs.SetInt("Clickrate", Clickrate);
           
        }
        if (Clickrate >= 1)
        {
            image.gameObject.SetActive(true);
        }
        if (Clickrate >= 2)
        {
            image1.gameObject.SetActive(true);
        }
        if (Clickrate >= 3)
        {
            image2.gameObject.SetActive(true);
        }
        if (Clickrate >= 4)
        {
            image3.gameObject.SetActive(true);
        }
        if (Clickrate >= 5)
        {
            image4.gameObject.SetActive(true);
        }
        if (Clickrate >= 6)
        {
            image5.gameObject.SetActive(true);
        }
        if (Clickrate == 7)
        {
            image6.gameObject.SetActive(true);
        }
        if (Clickrate >= 8)
        {
            Clickrate -= 1;
        }
        if (rate >= 8)
        {
            rate -= 1;
        }
        

    }
    public void Upgrade2()
    {
        if (money >= 1000)
        {
            image8.gameObject.SetActive(true);
        }
    }

    public void Update()
    {
        moneyText.text = "$" + money;
        PlayerPrefs.SetInt("Clickrate", Clickrate);
        if (Clickrate >= 1)
        {
            image.gameObject.SetActive(true);
        }
        if (Clickrate >= 2)
        {
            image1.gameObject.SetActive(true);
        }
        if (Clickrate >= 3)
        {
            image2.gameObject.SetActive(true);
        }
        if (Clickrate >= 4)
        {
            image3.gameObject.SetActive(true);
        }
        if (Clickrate >= 5)
        {
            image4.gameObject.SetActive(true);
        }
        if (Clickrate >= 6)
        {
            image5.gameObject.SetActive(true);
        }
        if (Clickrate == 7)
        {
            image6.gameObject.SetActive(true);
        }
        if (Clickrate >= 8)
        {
            Clickrate -= 1;
        }
        if (rate >= 8)
        {
            rate -= 1;
        }

    }

}
