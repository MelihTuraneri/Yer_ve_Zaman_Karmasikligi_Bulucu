#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct dosya
{
    char satir[50];
};
void for_kontrol(char ad[400],int for_yerleri[8], int dongu[2])
{
    int p = 0;
    int sayac = 0;
    char kontrol[3] = "for";
    char *ara_ptr = strstr(ad, kontrol);
    while(ara_ptr != NULL)
    {
        for_yerleri[p] = (ara_ptr - ad);
        p++;
        sayac++;
        ara_ptr = strstr(ara_ptr + 1, kontrol);
    }
    if(for_yerleri[0] != 0) dongu[0] = 1;
}
void int_yer_karmasikligi(struct dosya satirlar[],int yer_karmasiklik[12],int k, int fonks_indisi[10])
{
    int fonks_sayaci = 0;
    for(int j = 0; j < k; j++)
    {
        int p = 0;
        int sayac = 0;
        int virgul_sayisi = 0;
        int koseli_parantez_sayisi = 0;
        char kontrol[3] = "int";
        char *ara_ptr = strstr(satirlar[j].satir, kontrol);
        while(ara_ptr != NULL)
        {
            p++;
            sayac++;
            ara_ptr = strstr(ara_ptr + 1, kontrol);
        }
        if(sayac > 0)
        {
            for(int i = 0; satirlar[j].satir[i] != '\0'; i++)
            {
                if(satirlar[j].satir[i] == 40)
                {
                    sayac = 0;
                    fonks_indisi[fonks_sayaci] = j;
                    fonks_sayaci++;
                }

            }
        }
        if(sayac > 0)
        {
            for(int i = 0; satirlar[j].satir[i] != '\0'; i++)
            {
                if(satirlar[j].satir[i] == 91)
                    koseli_parantez_sayisi++;
            }
        }
        if(sayac == 1 && koseli_parantez_sayisi == 1)
        {
            yer_karmasiklik[4] = yer_karmasiklik[4] + 1;
            sayac = 0;
        }
        else if(sayac == 1 && koseli_parantez_sayisi == 2)
        {
            yer_karmasiklik[8] = yer_karmasiklik[8] + 1;
            sayac = 0;
        }
        if(sayac > 0)
        {
            for(int i = 0; satirlar[j].satir[i] != '\0'; i++)
            {
                if(satirlar[j].satir[i] == 91)
                    sayac = 0;
            }
        }
        if(sayac == 1)
        {
            for(int i = 0; satirlar[j].satir[i] != '\0'; i++)
            {
                if(satirlar[j].satir[i] == 44)
                    virgul_sayisi++;
            }
            yer_karmasiklik[0] = yer_karmasiklik[0] + (virgul_sayisi + 1);
        }
    }
}
void char_yer_karmasikligi(struct dosya satirlar[],int yer_karmasiklik[12],int k, int fonks_indisi[10])
{
    int fonks_sayaci = 0;
    for(int j = 0; j < k; j++)
    {
        int p = 0;
        int sayac = 0;
        int virgul_sayisi = 0;
        int koseli_parantez_sayisi = 0;
        char kontrol[3] = "char";
        char *ara_ptr = strstr(satirlar[j].satir, kontrol);
        while(ara_ptr != NULL)
        {
            p++;
            sayac++;
            ara_ptr = strstr(ara_ptr + 1, kontrol);
        }
        if(sayac > 0)
        {
            for(int i = 0; satirlar[j].satir[i] != '\0'; i++)
            {
                if(satirlar[j].satir[i] == 40)
                {
                    sayac = 0;
                    fonks_indisi[fonks_sayaci] = j;
                    fonks_sayaci++;
                }
            }
        }
        if(sayac > 0)
        {
            for(int i = 0; satirlar[j].satir[i] != '\0'; i++)
            {
                if(satirlar[j].satir[i] == 91)
                    koseli_parantez_sayisi++;
            }
        }
        if(sayac == 1 && koseli_parantez_sayisi == 1)
        {
            yer_karmasiklik[5] = yer_karmasiklik[5] + 1;
            sayac = 0;
        }
        else if(sayac == 1 && koseli_parantez_sayisi == 2)
        {
            yer_karmasiklik[9] = yer_karmasiklik[9] + 1;
            sayac = 0;
        }
        if(sayac > 0)
        {
            for(int i = 0; satirlar[j].satir[i] != '\0'; i++)
            {
                if(satirlar[j].satir[i] == 91)
                    sayac = 0;
            }
        }
        if(sayac == 1)
        {
            for(int i = 0; satirlar[j].satir[i] != '\0'; i++)
            {
                if(satirlar[j].satir[i] == 44)
                    virgul_sayisi++;
            }
            yer_karmasiklik[1] = yer_karmasiklik[1] + (virgul_sayisi + 1);
        }
    }
}
void float_yer_karmasikligi(struct dosya satirlar[],int yer_karmasiklik[12],int k, int fonks_indisi[10])
{
    int fonks_sayaci = 0;
    for(int j = 0; j < k; j++)
    {
        int p = 0;
        int sayac = 0;
        int virgul_sayisi = 0;
        int koseli_parantez_sayisi = 0;
        char kontrol[3] = "float";
        char *ara_ptr = strstr(satirlar[j].satir, kontrol);
        while(ara_ptr != NULL)
        {
            p++;
            sayac++;
            ara_ptr = strstr(ara_ptr + 1, kontrol);
        }
        if(sayac > 0)
        {
            for(int i = 0; satirlar[j].satir[i] != '\0'; i++)
            {
                if(satirlar[j].satir[i] == 40)
                {
                    sayac = 0;
                    fonks_indisi[fonks_sayaci] = j;
                    fonks_sayaci++;
                }
            }
        }
        if(sayac > 0)
        {
            for(int i = 0; satirlar[j].satir[i] != '\0'; i++)
            {
                if(satirlar[j].satir[i] == 91)
                    koseli_parantez_sayisi++;
            }
        }
        if(sayac == 1 && koseli_parantez_sayisi == 1)
        {
            yer_karmasiklik[6] = yer_karmasiklik[6] + 1;
            sayac = 0;
        }
        else if(sayac == 1 && koseli_parantez_sayisi == 2)
        {
            yer_karmasiklik[10] = yer_karmasiklik[10] + 1;
            sayac = 0;
        }
        if(sayac > 0)
        {
            for(int i = 0; satirlar[j].satir[i] != '\0'; i++)
            {
                if(satirlar[j].satir[i] == 91)
                    sayac = 0;
            }
        }
        if(sayac == 1)
        {
            for(int i = 0; satirlar[j].satir[i] != '\0'; i++)
            {
                if(satirlar[j].satir[i] == 44)
                    virgul_sayisi++;
            }
            yer_karmasiklik[2] = yer_karmasiklik[2] + (virgul_sayisi + 1);
        }
    }
}
void double_yer_karmasikligi(struct dosya satirlar[],int yer_karmasiklik[12],int k, int fonks_indisi[10])
{
    int fonks_sayaci = 0;
    for(int j = 0; j < k; j++)
    {
        int p = 0;
        int sayac = 0;
        int virgul_sayisi = 0;
        int koseli_parantez_sayisi = 0;
        char kontrol[3] = "double";
        char *ara_ptr = strstr(satirlar[j].satir, kontrol);
        while(ara_ptr != NULL)
        {
            p++;
            sayac++;
            ara_ptr = strstr(ara_ptr + 1, kontrol);
        }
        if(sayac > 0)
        {
            for(int i = 0; satirlar[j].satir[i] != '\0'; i++)
            {
                if(satirlar[j].satir[i] == 40)
                {
                    sayac = 0;
                    fonks_indisi[fonks_sayaci] = j;
                    fonks_sayaci++;
                }
            }
        }
        if(sayac > 0)
        {
            for(int i = 0; satirlar[j].satir[i] != '\0'; i++)
            {
                if(satirlar[j].satir[i] == 91)
                    koseli_parantez_sayisi++;
            }
        }
        if(sayac == 1 && koseli_parantez_sayisi == 1)
        {
            yer_karmasiklik[7] = yer_karmasiklik[7] + 1;
            sayac = 0;
        }
        else if(sayac == 1 && koseli_parantez_sayisi == 2)
        {
            yer_karmasiklik[11] = yer_karmasiklik[11] + 1;
            sayac = 0;
        }
        if(sayac > 0)
        {
            for(int i = 0; satirlar[j].satir[i] != '\0'; i++)
            {
                if(satirlar[j].satir[i] == 91)
                    sayac = 0;
            }
        }
        if(sayac == 1)
        {
            for(int i = 0; satirlar[j].satir[i] != '\0'; i++)
            {
                if(satirlar[j].satir[i] == 44)
                    virgul_sayisi++;
            }
            yer_karmasiklik[3] = yer_karmasiklik[3] + (virgul_sayisi + 1);
        }
    }
}
void hiyerarsi_belirleme_fonk(int hiyerarsi_dizisi[],int dongu_hiyerarsi_belirleme[],int for_yerleri[5],int for_sayisi_sayaci,int suslu_sayaci)
{
    int for_yerlerinin_sayaci = 0;
    int dongu_hiyerarsi_sayaci = 0;
    for(int i = 0; i < (suslu_sayaci + for_sayisi_sayaci); i++)
    {
        if(for_yerleri[for_yerlerinin_sayaci] == hiyerarsi_dizisi[i])
        {
            if(hiyerarsi_dizisi[i + 2] == for_yerleri[for_yerlerinin_sayaci + 1])
            {
                dongu_hiyerarsi_belirleme[dongu_hiyerarsi_sayaci + 1] = dongu_hiyerarsi_belirleme[dongu_hiyerarsi_sayaci] + 1;
                dongu_hiyerarsi_sayaci++;
                for_yerlerinin_sayaci++;
                if(for_sayisi_sayaci == for_yerlerinin_sayaci) break;
                continue;
            }
            if(hiyerarsi_dizisi[i + 3] == for_yerleri[for_yerlerinin_sayaci + 1])
            {
                dongu_hiyerarsi_belirleme[dongu_hiyerarsi_sayaci + 1] = dongu_hiyerarsi_belirleme[dongu_hiyerarsi_sayaci];
                dongu_hiyerarsi_sayaci++;
                for_yerlerinin_sayaci++;
                if(for_sayisi_sayaci == for_yerlerinin_sayaci)break;
                continue;
            }
            if(hiyerarsi_dizisi[i + 4] == for_yerleri[for_yerlerinin_sayaci + 1])
            {
                dongu_hiyerarsi_belirleme[dongu_hiyerarsi_sayaci + 1] = dongu_hiyerarsi_belirleme[dongu_hiyerarsi_sayaci] - 1;
                dongu_hiyerarsi_sayaci++;
                for_yerlerinin_sayaci++;
                if(for_sayisi_sayaci == for_yerlerinin_sayaci)break;
                continue;
            }
        }
    }
}
void yer_karmasiklik_yazdirma(int yer_karmasiklik[12])
{
    int kendine_gore_toplu[3] = {0,0,0};
    int sayac = 0;
    int toplam = 0;
    for(int i = 0; i < 12; i++)
    {
        if(i == 4 || i == 8)
        {
            sayac++;
        }
        if(i == 0 || i == 4 || i == 8)
        {
            kendine_gore_toplu[sayac] = kendine_gore_toplu[sayac] + 4*yer_karmasiklik[i];
        }
        else if(i == 1 || i == 5 || i == 9)
        {
            kendine_gore_toplu[sayac] = kendine_gore_toplu[sayac] + 1*yer_karmasiklik[i];
        }
        else if(i ==2 || i == 6 || i == 10)
        {
            kendine_gore_toplu[sayac] = kendine_gore_toplu[sayac] + 4*yer_karmasiklik[i];
        }
        else if(i == 3 || i == 7 || i == 11)
        {
            kendine_gore_toplu[sayac] = kendine_gore_toplu[sayac] + 8*yer_karmasiklik[i];
        }
    }
    printf("\nYer Karmasikligi ---> (");
    for(int i = 0; i < 3; i++)
    {
        if(i == 0 && kendine_gore_toplu[2] != 0)
        {
            printf("%d(n^2) + ", kendine_gore_toplu[2]);
        }
        else if(i == 1 && kendine_gore_toplu[1] != 0)
        {
            printf("%dn + ", kendine_gore_toplu[1]);
        }
        else if(i == 2 && kendine_gore_toplu[0] != 0)
        {
            printf("%d ", kendine_gore_toplu[0]);
        }
    }
    if(kendine_gore_toplu[2] != 0)
    {
        printf("O(n^2))");
    }
    else if(kendine_gore_toplu[1] != 0)
    {
        printf("O(n))");
    }
    else if(kendine_gore_toplu[0] != 0)
    {
        printf("O(1))");
    }
    printf("\n\n");
}
int algoritma_karmasiklik_bulma_fonksu(int for_nleri[], int dongu_hiyerarsi_belirleme[], int for_sayisi_sayaci, int suslu_sayaci)
{
    int for_sayisi_sayaci_cakmasi = for_sayisi_sayaci;
    int babalarin_sayaci = 0;
    int sayac1 = 0;
    int artik_yeter_karisikligi[5] = {1,1,1,1,1};
    int sayac2 = 0;
    for(int i = 0; i < for_sayisi_sayaci; i++)
    {
        if(dongu_hiyerarsi_belirleme[i] == 1)
            babalarin_sayaci++;
    }
    int babalarin_yerleri[babalarin_sayaci];
    for(int i = 0; i < for_sayisi_sayaci; i++)
    {
        if(dongu_hiyerarsi_belirleme[i] == 1)
        {
            babalarin_yerleri[sayac1] = i;
            sayac1++;
        }
    }
    sayac1 = 0;
    for(int i = babalarin_yerleri[sayac1]; i < for_sayisi_sayaci + 1; i++)
    {
        if(dongu_hiyerarsi_belirleme[i + 1] == 1)
        {
            artik_yeter_karisikligi[sayac2] = for_nleri[i];
            sayac1++;
            sayac2++;
            artik_yeter_karisikligi[sayac2] = for_nleri[i + 1];
            if(sayac2 == for_sayisi_sayaci || babalarin_yerleri[sayac1] == for_sayisi_sayaci) break;
            continue;
        }
        else if(dongu_hiyerarsi_belirleme[i] == dongu_hiyerarsi_belirleme[i + 1] - 1)
        {
            if((for_nleri[i] == 1 && for_nleri[i + 1] == 1))
            {
                artik_yeter_karisikligi[sayac2] = 2;
                for_nleri[i + 1] = 2;
            }
            else if((for_nleri[i] == 2 && for_nleri[i + 1] == 1) || (for_nleri[i] == 1 && for_nleri[i + 1] == 2))
            {
                artik_yeter_karisikligi[sayac2] = 3;
                for_nleri[i + 1] = 3;
            }
            else if((for_nleri[i] == 4 && for_nleri[i + 1] == 1) || (for_nleri[i] == 1 && for_nleri[i + 1] == 4))
            {
                artik_yeter_karisikligi[sayac2] = 5;
                for_nleri[i + 1] = 5;
            }
            else if((for_nleri[i] == 4 && for_nleri[i + 1] == 2) || (for_nleri[i] == 2 && for_nleri[i + 1] == 4))
            {
                artik_yeter_karisikligi[sayac2] = 6;
                for_nleri[i + 1] = 6;
            }
            else if((for_nleri[i] == 5 && for_nleri[i + 1] == 1) || (for_nleri[i] == 1 && for_nleri[i + 1] == 5))
            {
                artik_yeter_karisikligi[sayac2] = 6;
                for_nleri[i + 1] = 6;
            }
        }
        else if(dongu_hiyerarsi_belirleme[i] == dongu_hiyerarsi_belirleme[i + 1])
        {
            sayac2++;
            if((for_nleri[i + 1] == 1 && dongu_hiyerarsi_belirleme[sayac1] == 1))
            {
                artik_yeter_karisikligi[sayac2] = 2;
                for_nleri[i + 1] = 2;
            }
            else if((for_nleri[i + 1] == 2 && dongu_hiyerarsi_belirleme[sayac1] == 1) || (for_nleri[i + 1] == 1 && dongu_hiyerarsi_belirleme[sayac1] == 2))
            {
                artik_yeter_karisikligi[sayac2] = 3;
                for_nleri[i + 1] = 3;
            }
            else if((for_nleri[i + 1] == 4 && dongu_hiyerarsi_belirleme[sayac1] == 1) || (for_nleri[i + 1] == 1 && dongu_hiyerarsi_belirleme[sayac1] == 4))
            {
                artik_yeter_karisikligi[sayac2] = 5;
                for_nleri[i + 1] = 5;
            }
            else if((for_nleri[i + 1] == 4 && dongu_hiyerarsi_belirleme[sayac1] == 2) || (for_nleri[i + 1] == 2 && dongu_hiyerarsi_belirleme[sayac1] == 4))
            {
                artik_yeter_karisikligi[sayac2] = 6;
                for_nleri[i + 1] = 6;
            }
            else if((for_nleri[i + 1] == 5 && dongu_hiyerarsi_belirleme[sayac1] == 1) || (for_nleri[i + 1] == 1 && dongu_hiyerarsi_belirleme[sayac1] == 5))
            {
                artik_yeter_karisikligi[sayac2] = 6;
                for_nleri[i + 1] = 6;
            }
        }
        else if(dongu_hiyerarsi_belirleme[i] > dongu_hiyerarsi_belirleme[i + 1])
        {
            sayac2++;
            if((for_nleri[i + 1] == 1 && dongu_hiyerarsi_belirleme[sayac1] == 1))
            {
                artik_yeter_karisikligi[sayac2] = 2;
                for_nleri[i + 1] = 2;
            }
            else if((for_nleri[i + 1] == 2 && dongu_hiyerarsi_belirleme[sayac1] == 1) || (for_nleri[i + 1] == 1 && dongu_hiyerarsi_belirleme[sayac1] == 2))
            {
                artik_yeter_karisikligi[sayac2] = 3;
                for_nleri[i + 1] = 3;
            }
            else if((for_nleri[i + 1] == 4 && dongu_hiyerarsi_belirleme[sayac1] == 1) || (for_nleri[i + 1] == 1 && dongu_hiyerarsi_belirleme[sayac1] == 4))
            {
                artik_yeter_karisikligi[sayac2] = 5;
                for_nleri[i + 1] = 5;
            }
            else if((for_nleri[i + 1] == 4 && dongu_hiyerarsi_belirleme[sayac1] == 2) || (for_nleri[i + 1] == 2 && dongu_hiyerarsi_belirleme[sayac1] == 4))
            {
                artik_yeter_karisikligi[sayac2] = 6;
                for_nleri[i + 1] = 6;
            }
            else if((for_nleri[i + 1] == 5 && dongu_hiyerarsi_belirleme[sayac1] == 1) || (for_nleri[i + 1] == 1 && dongu_hiyerarsi_belirleme[sayac1] == 5))
            {
                artik_yeter_karisikligi[sayac2] = 6;
                for_nleri[i + 1] = 6;
            }
        }
    }
    for(int i = 0; i < 5; i++)
    {
        if(artik_yeter_karisikligi[i] == 1)artik_yeter_karisikligi[i] = 2;
        else if(artik_yeter_karisikligi[i] == 2)artik_yeter_karisikligi[i] = 4;
        else if(artik_yeter_karisikligi[i] == 3)artik_yeter_karisikligi[i] = 5;
        else if(artik_yeter_karisikligi[i] == 4)artik_yeter_karisikligi[i] = 1;
        else if(artik_yeter_karisikligi[i] == 5)artik_yeter_karisikligi[i] = 3;
        else if(artik_yeter_karisikligi[i] == 6)artik_yeter_karisikligi[i] = 4;
    }
    int en_buyuk = 0;
    for(int i = 0; i < 5; i++)
    {
        if(en_buyuk < artik_yeter_karisikligi[i])en_buyuk = artik_yeter_karisikligi[i];
    }
    if(en_buyuk == 1)printf("\n\nFor Zaman Karmasikligi --> O(logn)\n");
    else if(en_buyuk == 2)printf("\n\nFor Zaman Karmasikligi --> O(n)\n");
    else if(en_buyuk == 3)printf("\n\nFor Zaman Karmasikligi --> O(nlogn)\n");
    else if(en_buyuk == 4)printf("\n\nFor Zaman Karmasikligi --> O(n^2)\n");
    else if(en_buyuk == 5)printf("\n\nFor Zaman Karmasikligi --> O(n^3)\n");
}

void while_kontrol(struct dosya satirlar[],char ad[400],int while_yerleri[2], int dongu[2],int k,int ismini_bilmedigim[2])
{
    ismini_bilmedigim[1] = 0;
    ismini_bilmedigim[0] = 0;
    int p = 0;
    int sayac = 0;
    int satirlarlar[3] = {0,0,0};
    int satir_karmasikligi[3] = {1,1,1};
    int while_satir_uzunlugu = 0;
    int open_close = 0;
    int open_close2 = 0;
    int kapali_parantez,acik_parantez,isaretci;
    char *ara_ptr = strstr(ad, "while");
    while(ara_ptr != NULL)
    {
        while_yerleri[p] = (ara_ptr - ad);
        p++;
        sayac++;
        ara_ptr = strstr(ara_ptr + 1, "while");
    }
    if(while_yerleri[0] != 0) dongu[1] = 1;
    if(while_yerleri[0] != 0)
    {
        for(int j = while_yerleri[0]; ad[j] != '\n'; j++)
        {
            while_satir_uzunlugu++;
            if(ad[j] == 60)
            {
                open_close = 1;
                isaretci = j;
            }
            if(ad[j] == 62)
            {
                isaretci = j;
            }
            if(ad[j] == 40)
            {
                acik_parantez = j;
            }
            if(ad[j] == 41)
            {
                kapali_parantez = j;
            }
        }
        char aranan[10] = {""};
        char aranan1[10] = {""};
        char while_satiri[while_satir_uzunlugu];
        int uzunluk = 0;
        int sayaccccc = 0;
        if(open_close == 1)
        {
            for(int j = acik_parantez + 1; ad[j] != 60; j++)
            {
                aranan[sayaccccc] = ad[j];
                sayaccccc++;
            }
        }
        else
        {
            for(int j = isaretci + 2; ad[j] != 41; j++)
            {
                aranan1[sayaccccc] = ad[j];
                sayaccccc++;
            }
        }
        char asil_aranan[sayaccccc];
        char asil_aranan1[sayaccccc];
        if(open_close == 1)
        {
            for(int j = 0; aranan[j] != 32 ; j++)
            {
                asil_aranan[j] = aranan[j];
            }
        }
        else
        {
            for(int j = 0; aranan1[j] != 32; j++)
            {
                asil_aranan1[j] = aranan1[j];
            }
        }
        for(int j = while_yerleri[0]; ad[j] != 59; j++)
        {
            while_satiri[uzunluk] = ad[j];
            uzunluk++;
            if(uzunluk == while_satir_uzunlugu + 1) break;
        }
        if(ad[while_yerleri[0] - 1] == 125) open_close2 = 1;
        int alt,ust;
        if(open_close2 == 1)
        {
            for(int i = 0; i < k; i++)
            {
                ara_ptr = strstr(satirlar[i].satir, "while");
                while(ara_ptr != NULL)
                {
                    ara_ptr = strstr(ara_ptr + 1, "while");
                    ust = i;
                    break;
                }
            }
            for(int i = 0; i < k; i++)
            {
                ara_ptr = strstr(satirlar[i].satir, "do{");
                while(ara_ptr != NULL)
                {
                    ara_ptr = strstr(ara_ptr + 1, "do{");
                    alt = i;
                    break;
                }
            }
            int satir_sayaci = 0;
            for(int i = 0; i < k; i++)
            {
                for(int j = 0; satirlar[i].satir[j] != '\n'; j++)
                {
                    if(satirlar[i].satir[j] == 40)break;


                    if(satirlar[i].satir[j] == 61)
                    {
                        ismini_bilmedigim[1]++;
                    }
                }
            }
            for(int i = alt; i < ust; i++)
            {
                for(int j = 0; satirlar[i].satir[j] != '\n'; j++)
                {
                    if(satirlar[i].satir[j] == 40)break;
                    if(satirlar[i].satir[j] == 61)
                    {
                        ismini_bilmedigim[0]++;
                    }
                }
            }
            for(int i = alt; i < ust; i++)
            {
                if(open_close == 1)
                {
                    ara_ptr = strstr(satirlar[i].satir, asil_aranan);
                    while(ara_ptr != NULL)
                    {
                        ara_ptr = strstr(ara_ptr + 1, asil_aranan);
                        satirlarlar[satir_sayaci] = i;
                        satir_sayaci++;
                        continue;
                    }
                }
                else
                {
                    ara_ptr = strstr(satirlar[i].satir, asil_aranan1);
                    while(ara_ptr != NULL)
                    {
                        ara_ptr = strstr(ara_ptr + 1, asil_aranan1);
                        satirlarlar[satir_sayaci] = i;
                        satir_sayaci++;
                        continue;
                    }
                }
            }
            int while_karmasiklik_satiri[satir_sayaci];
            for(int i = 0; i < satir_sayaci; i++)
            {
                while_karmasiklik_satiri[i] = 1;
            }
            if(open_close == 1)
            {
                for(int i = 0; i < satir_sayaci; i++)
                {
                    for(int a = 0; satirlar[satirlarlar[i]].satir[a] != '\n'; a++)
                    {
                        if(satirlar[satirlarlar[i]].satir[a] == 42 || satirlar[satirlarlar[i]].satir[a] == 47)
                        {
                            while_karmasiklik_satiri[i] = 4;
                        }
                        else if(satirlar[satirlarlar[i]].satir[a] == 43 || satirlar[satirlarlar[i]].satir[a] == 45)
                        {
                            if(satirlar[satirlarlar[i]].satir[a + 1] == 43 || satirlar[satirlarlar[i]].satir[a + 1] == 45 || isdigit(satirlar[satirlarlar[i]].satir[a + 1]))
                            {
                                while_karmasiklik_satiri[i] = 1;
                                break;
                            }
                            else while_karmasiklik_satiri[i] = 4;
                        }
                    }
                }
                for(int i = 0; i < satir_sayaci; i++)
                {
                    if(while_karmasiklik_satiri[i] == 1)
                    {
                        printf("\nDo While Zaman Karmasikligi --> O(n)\n");
                        printf("\nCalisma Suresi --> T(n) = %dn + %d\n",ismini_bilmedigim[0] + 1, ismini_bilmedigim[1] - ismini_bilmedigim[0] + 1);
                        break;
                    }
                    else if(i + 1 == satir_sayaci)
                    {
                        printf("\nDo While Zaman Karmasikligi --> O(logn)");
                        printf("\nCalisma Suresi --> T(n) = %dlogn + %d\n",ismini_bilmedigim[0] + 1, ismini_bilmedigim[1] - ismini_bilmedigim[0] + 1);
                    }
                }
            }
            else
            {
                for(int i = 0; i < satir_sayaci; i++)
                {
                    for(int a = 0; satirlar[satirlarlar[i]].satir[a] != '\n'; a++)
                    {
                        if(satirlar[satirlarlar[i]].satir[a] == 42 || satirlar[satirlarlar[i]].satir[a] == 47)
                        {
                            while_karmasiklik_satiri[i] = 4;
                        }
                        else if(satirlar[satirlarlar[i]].satir[a] == 43 || satirlar[satirlarlar[i]].satir[a] == 45)
                        {
                            if(satirlar[satirlarlar[i]].satir[a + 1] == 43 || satirlar[satirlarlar[i]].satir[a + 1] == 45 || isdigit(satirlar[satirlarlar[i]].satir[a + 1]))
                            {
                                while_karmasiklik_satiri[i] = 1;
                                break;
                            }
                            else while_karmasiklik_satiri[i] = 4;
                        }
                    }
                }
                for(int i = 0; i < satir_sayaci; i++)
                {
                    if(while_karmasiklik_satiri[i] == 1)
                    {
                        printf("\nDo While Zaman Karmasikligi --> O(n)\n");
                        printf("\nCalisma Suresi --> T(n) = %dn + %d\n",ismini_bilmedigim[0] + 1, ismini_bilmedigim[1] - ismini_bilmedigim[0] + 1);
                        break;
                    }
                    else if(i + 1 == satir_sayaci)
                    {
                        printf("\nDo While Zaman Karmasikligi --> O(logn)\n");
                        printf("\nCalisma Suresi --> T(n) = %dlogn + %d\n",ismini_bilmedigim[0] + 1, ismini_bilmedigim[1] - ismini_bilmedigim[0] + 1);
                    }
                }
            }
        }
        else
        {
            for(int i = 0; i < k; i++)
            {
                char *ara_ptr2 = strstr(satirlar[i].satir, "while");
                while(ara_ptr2 != NULL)
                {
                    ara_ptr2 = strstr(ara_ptr2 + 1, "while");
                    alt = i;
                    break;
                }
            }
            for(int i = 0; i < k; i++)
            {
                for(int j = 0; satirlar[i].satir[j] != '\n'; j++)
                {
                    if(satirlar[i].satir[j] == 125)ust = i;
                }
            }
            for(int i = 0; i < k; i++)
            {
                for(int j = 0; satirlar[i].satir[j] != '\n'; j++)
                {
                    if(satirlar[i].satir[j] == 40)break;
                    if(satirlar[i].satir[j] == 61)
                    {
                        ismini_bilmedigim[1]++;
                    }
                }
            }
            for(int i = alt + 1; i < ust + 1; i++)
            {
                for(int j = 0; satirlar[i].satir[j] != '\n'; j++)
                {
                    if(satirlar[i].satir[j] == 40)break;
                    if(satirlar[i].satir[j] == 61)
                    {
                        ismini_bilmedigim[0]++;
                    }
                }
            }
            int satir_sayaci = 0;
            if(open_close == 1)
            {
                for(int i = alt + 1; i < ust + 1; i++)
                {
                    char *ara_ptr2 = strstr(satirlar[i].satir, asil_aranan);
                    while(ara_ptr2 != NULL)
                    {
                        ara_ptr2 = strstr(ara_ptr2 + 1, asil_aranan);
                        satirlarlar[satir_sayaci] = i;
                        satir_sayaci++;
                        continue;
                    }
                }
            }
            else
            {
                for(int i = alt + 1; i < ust + 1; i++)
                {
                    char *ara_ptr2 = strstr(satirlar[i].satir, asil_aranan1);
                    while(ara_ptr2 != NULL)
                    {
                        ara_ptr2 = strstr(ara_ptr2 + 1, asil_aranan1);
                        satirlarlar[satir_sayaci] = i;
                        satir_sayaci++;
                        continue;
                    }
                }
            }
            int while_karmasiklik_satiri[satir_sayaci];
            for(int i = 0; i < satir_sayaci; i++)
            {
                while_karmasiklik_satiri[i] = 1;
            }
            if(open_close == 1)
            {
                for(int i = 0; i < satir_sayaci; i++)
                {
                    for(int a = 0; satirlar[satirlarlar[i]].satir[a] != '\n'; a++)
                    {
                        if(satirlar[satirlarlar[i]].satir[a] == 42 || satirlar[satirlarlar[i]].satir[a] == 47)
                        {
                            while_karmasiklik_satiri[i] = 4;
                        }
                        else if(satirlar[satirlarlar[i]].satir[a] == 43 || satirlar[satirlarlar[i]].satir[a] == 45)
                        {
                            if(satirlar[satirlarlar[i]].satir[a + 1] == 43 || satirlar[satirlarlar[i]].satir[a + 1] == 45 || isdigit(satirlar[satirlarlar[i]].satir[a + 1]))
                            {
                                while_karmasiklik_satiri[i] = 1;
                                break;
                            }
                            else while_karmasiklik_satiri[i] = 4;
                        }
                    }
                }
                for(int i = 0; i < satir_sayaci; i++)
                {
                    if(while_karmasiklik_satiri[i] == 1)
                    {
                        printf("\nWhile Zaman Karmasikligi --> O(n)\n");
                        printf("\nCalisma Suresi --> T(n) = %dn + %d\n",ismini_bilmedigim[0] + 1, ismini_bilmedigim[1] - ismini_bilmedigim[0] + 1);
                        break;
                    }
                    else if(i + 1 == satir_sayaci)
                    {
                        printf("\nWhile Zaman Karmasikligi --> O(logn)\n");
                        printf("\nCalisma Suresi --> T(n) = %dlogn + %d\n", ismini_bilmedigim[0] + 1, ismini_bilmedigim[1] - ismini_bilmedigim[0] + 1);
                    }
                }
            }
            else
            {
                for(int i = 0; i < satir_sayaci; i++)
                {
                    for(int a = 0; satirlar[satirlarlar[i]].satir[a] != '\n'; a++)
                    {
                        if(satirlar[satirlarlar[i]].satir[a] == 42 || satirlar[satirlarlar[i]].satir[a] == 47)
                        {
                            while_karmasiklik_satiri[i] = 4;
                        }
                        else if(satirlar[satirlarlar[i]].satir[a] == 43 || satirlar[satirlarlar[i]].satir[a] == 45)
                        {
                            if(satirlar[satirlarlar[i]].satir[a + 1] == 43 || satirlar[satirlarlar[i]].satir[a + 1] == 45 || isdigit(satirlar[satirlarlar[i]].satir[a + 1]))
                            {
                                while_karmasiklik_satiri[i] = 1;
                                break;
                            }
                            else while_karmasiklik_satiri[i] = 4;
                        }
                    }
                }
                for(int i = 0; i < satir_sayaci; i++)
                {
                    if(while_karmasiklik_satiri[i] == 1)
                    {
                        printf("\nWhile Zaman Karmasikligi --> O(n)\n");
                        printf("\nCalisma Suresi --> T(n) = %dn + %d\n",ismini_bilmedigim[0] + 1, ismini_bilmedigim[1] - ismini_bilmedigim[0] + 1);
                        break;
                    }
                    else if(i + 1 == satir_sayaci)
                    {
                        printf("\nWhile Zaman Karmasikligi --> O(logn)\n");
                        printf("\nCalisma Suresi --> T(n) = %dlogn + %d\n",ismini_bilmedigim[0] + 1, ismini_bilmedigim[1] - ismini_bilmedigim[0] + 1);
                    }
                }
            }
        }
    }
}

void recursive_bulma(struct dosya satirlar[], int fonks_indisi[10], int k, int ismini_bilmedigim[2])
{
    ismini_bilmedigim[1] = 0;
    ismini_bilmedigim[0] = 0;
    int sayac = 0;
    int mainden_onceki_satir;
    int asil_rec_satiri,ilk,son;
    for(int i = fonks_indisi[sayac]; fonks_indisi[sayac] != - 1; sayac++)
    {
        int sayac2 = 0;
        char *ara_ptr = strstr(satirlar[fonks_indisi[sayac]].satir, "main");
        while(ara_ptr != NULL)
        {
            mainden_onceki_satir = fonks_indisi[sayac];
            sayac2++;
            ara_ptr = strstr(ara_ptr + 1, "main");
        }
        if(sayac2 != 0)fonks_indisi[sayac] = -1;
        for(int j = 0; satirlar[fonks_indisi[sayac]].satir[j] != '\n'; j++)
        {
            if(satirlar[fonks_indisi[sayac]].satir[j] == 59)
            {
                fonks_indisi[sayac] = -1;
            }
        }
    }
    for(int i = 0; i < k; i++)
    {
        for(int j = 0; satirlar[i].satir[j] != '\n'; j++)
        {
            if(satirlar[i].satir[j] == 40)break;
            if(satirlar[i].satir[j] == 61)
            {
                ismini_bilmedigim[1]++;
            }
        }
    }
    for(int i = fonks_indisi[0]; i < mainden_onceki_satir - 1; i++)
    {
        for(int j = 0; satirlar[i].satir[j] != '\n'; j++)
        {
            if(satirlar[i].satir[j] == 40)break;
            if(satirlar[i].satir[j] == 61)
            {
                ismini_bilmedigim[0]++;
            }
        }
    }
    int sayac_calisir_mi;
    for(int i = 0; i < 10; i++)
    {
        if(fonks_indisi[i] != - 1)
        {
            sayac_calisir_mi = 1;
            break;
        }
    }
    if(sayac_calisir_mi == 1)
    {
        for(int i = 0; fonks_indisi[i] != -1; i++)
        {
            asil_rec_satiri = fonks_indisi[i];
        }
        sayac = 0;
        for(int i = 0; satirlar[asil_rec_satiri].satir[i] != '\n'; i++)
        {
            if(sayac == 0 && satirlar[asil_rec_satiri].satir[i] == 32)
            {
                ilk = i;
                sayac++;
            }
            else if(sayac == 1 && satirlar[asil_rec_satiri].satir[i] == 32)
            {
                son = i;
                sayac = -1;
            }
        }
        char rec_fonks_ismi[son - ilk - 1];
        int sayac4001 = 0;
        int sayac40 = 0;
        for(int i = ilk + 1; i < son; i++)
        {
            rec_fonks_ismi[sayac4001] = satirlar[asil_rec_satiri].satir[i];
            sayac4001++;
            if(sayac4001 > son - ilk - 1)break;
        }
        char asil_rec_fonks_ismi[son - ilk - 1];
        for(int i = 0; i < son - ilk - 1; i++)
        {
            asil_rec_fonks_ismi[i] = rec_fonks_ismi[i];
        }
        int rec_fonksiyon_yerleri[5] = {-1,-1,-1,-1,-1};
        sayac4001 = 0;
        for(int i = 0; i < k; i++)
        {
            if(satirlar[i].satir[0] == 125) break;
            for(int j = 0; satirlar[i].satir[j] != '\n'; j++)
            {
                if(satirlar[i].satir[j] == asil_rec_fonks_ismi[sayac4001])
                {
                    sayac4001++;
                    if(sayac4001 == son - ilk - 1)
                    {
                        rec_fonksiyon_yerleri[sayac40] = i;
                        sayac40++;
                        continue;
                    }
                }
                else
                {
                    sayac4001 = 0;
                }
            }
        }
        for(int i = 0; i < 5; i++)
        {
            if(fonks_indisi[0] == rec_fonksiyon_yerleri[i])
            {
                rec_fonksiyon_yerleri[i] = - 1;
            }
        }
        sayac4001 = 0;
        for(int i = 0; i < 5; i++)
        {
            if(rec_fonksiyon_yerleri[i] == rec_fonksiyon_yerleri[i + 1] && rec_fonksiyon_yerleri[i] != - 1)sayac4001++;
        }
        if(sayac4001 != 0)
        {
            printf("\n\nRecursive Zaman Karmasikligi --> O(%d^n)\n",sayac4001 + 1);
            printf("\nCalisma Suresi --> T(n) = %d.%d^n + %d\n",ismini_bilmedigim[0], sayac4001 + 1, ismini_bilmedigim[1] - ismini_bilmedigim[0] + 1);
        }
        int baska_sayac = 0;
        int sayac_54;
        for(int i  = 0; i < 5; i++)
        {
            if(rec_fonksiyon_yerleri[i] != - 1)
            {
                sayac_54 = rec_fonksiyon_yerleri[i];
            }
        }
        for(int j = 0; satirlar[sayac_54].satir[j] != 41; j++)
        {
            if(satirlar[sayac_54].satir[j] == 40)baska_sayac++;
            if(baska_sayac != 0 && (sayac4001 == 0))
            {
                if(satirlar[sayac_54].satir[j] == 43 || satirlar[sayac_54].satir[j] == 45)
                {
                    printf("\n\nRecursive Zaman Karmasikligi --> O(n)\n");
                    printf("\nCalisma Suresi --> T(n) = %d.n + %d\n",ismini_bilmedigim[0], ismini_bilmedigim[1] - ismini_bilmedigim[0] + 1);
                    break;
                }
                else if(satirlar[sayac_54].satir[j] == 42 || satirlar[sayac_54].satir[j] == 47)
                {
                    printf("\n\nRecursive Zaman Karmasikligi --> O(logn)\n");
                    printf("\nCalisma Suresi --> T(n) = %d.logn + %d\n",ismini_bilmedigim[0], ismini_bilmedigim[1] - ismini_bilmedigim[0] + 1);
                    break;
                }
            }
        }
    }
}

int main()
{
    FILE *fp;
    FILE *fp0;
    int k = 0,n = 0,for_sayisi_sayaci = 0,ad_boyut = 0,suslu_sayaci = 0,p = 0,sayac = 0;
    int suslu_yerleri[24] = {0};
    int for_yerleri[8] = {0};
    int while_yerleri[2] = {0};
    int yer_karmasiklik[12] = {0};
    int ismini_bilmedigim[2] = {0,0};
    int dongu[2] = {0};
    int fonks_indisi[10] = {-1,-1,-1,-1,-1,-1,-1,-1,-1,-1};
    char ch;
    fp0=fopen("text.txt", "r");
    while(feof(fp0) == NULL)
    {
        ch=getc(fp0);
        ad_boyut++;//   printf("%c",ch);
        if(ch =='\n')
        {
            k++;
        }
        if(ch == 32)
        {
            n++;
        }
    }//  printf("%d %d\n",ad_boyut - 1,n);
    struct dosya satirlar[k];
    printf("Dosya aciliyor!\n\n...\n\n");
    if((fp=fopen("text.txt", "r+"))==NULL)
    {
        printf("...\n\nDosya acilamadi...\n");
        exit(0);
    }
    else printf("...\n\nDosya acildi!\n\n");
    char ad[400] = {""};
    while(p < k + 1)
    {
        fgets(satirlar[p].satir, 50,fp);
        printf("%s", satirlar[p].satir);
        strcat(ad,satirlar[p].satir);
        p++;
    }
    for(int j = 0; ad[j] != '\0'; j++)sayac++;
    int_yer_karmasikligi(satirlar,yer_karmasiklik,k,fonks_indisi);
    char_yer_karmasikligi(satirlar,yer_karmasiklik,k,fonks_indisi);
    float_yer_karmasikligi(satirlar,yer_karmasiklik,k,fonks_indisi);
    double_yer_karmasikligi(satirlar,yer_karmasiklik,k,fonks_indisi);
    recursive_bulma(satirlar,fonks_indisi,k, ismini_bilmedigim);
    for_kontrol(ad,for_yerleri,dongu);
    while_kontrol(satirlar,ad,while_yerleri,dongu,k,ismini_bilmedigim);
    if(dongu[0] == 1)
    {
        for(int j = 0; for_yerleri[j] != 0; j++)
        {
            for_sayisi_sayaci++;
        }
        for(int j = 0; ad[j] != '\0'; j++)
        {
            if(ad[j] == 123 || ad[j] == 125)
            {
                suslu_yerleri[suslu_sayaci] = j;
                suslu_sayaci++;
            }
        }
        int dongu_hiyerarsi_belirleme[for_sayisi_sayaci];
        int for_nleri[for_sayisi_sayaci];
        for(int j = 0; j < for_sayisi_sayaci; j++)
        {
            for_nleri[j] = 1;
        }
        for(int j = 0; j < for_sayisi_sayaci; j++)
        {
            dongu_hiyerarsi_belirleme[j] = 1;
        }
        int hiyerarsi_dizisi[for_sayisi_sayaci + suslu_sayaci];
        for(int j = 0; j < (for_sayisi_sayaci + suslu_sayaci); j++)
        {
            hiyerarsi_dizisi[j] = suslu_yerleri[j];
        }
        for(int j = 0; j < for_sayisi_sayaci; j++)
        {
            hiyerarsi_dizisi[suslu_sayaci + j] = for_yerleri[j];
        }
        int temp;
        for(int j = 1; j < (for_sayisi_sayaci + suslu_sayaci); j++)
        {
            for(int a = 0; a < (for_sayisi_sayaci + suslu_sayaci - j); a++)
            {
                if(hiyerarsi_dizisi[a] > hiyerarsi_dizisi[a+1])
                {
                    temp =  hiyerarsi_dizisi[a + 1];
                    hiyerarsi_dizisi[a + 1] = hiyerarsi_dizisi[a];
                    hiyerarsi_dizisi[a] = temp;
                }
            }
        }
        hiyerarsi_belirleme_fonk(hiyerarsi_dizisi,dongu_hiyerarsi_belirleme,for_yerleri,for_sayisi_sayaci,suslu_sayaci);
        for(int i = 0; i < for_sayisi_sayaci; i++)
        {
            for(int j = for_yerleri[i]; ad[j] != 123; j++)
            {
                if(ad[j] == 42 || ad[j] == 47)
                {
                    for_nleri[i] = 4;
                }
            }
        }
        algoritma_karmasiklik_bulma_fonksu(for_nleri,dongu_hiyerarsi_belirleme,for_sayisi_sayaci,suslu_sayaci);
    }
    yer_karmasiklik_yazdirma(yer_karmasiklik);
    return 0;
}
