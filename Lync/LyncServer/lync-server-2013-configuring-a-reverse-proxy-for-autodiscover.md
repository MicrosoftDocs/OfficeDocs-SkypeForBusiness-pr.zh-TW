---
title: Lync Server 2013： 設定自動探索的反向 proxy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c50704508c09d1f30a9fb8e31060e2a3b69885d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a>在 Lync Server 2013 中設定自動探索的反向 proxy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-12-12_

自動探索和使用自動探索的用戶端支援需要修改現有的 web 發行規則或建立新的 web 發行規則的反向 proxy。 修改或建立新的發佈規則不取決於更新或更新主體替代名稱清單，反向 proxy 憑證上的決策。

如果您決定使用 HTTPS 執行初始 Lync Server 2013 自動探索服務要求，並更新反向 proxy 憑證上的主體替代名稱清單，您需要在將更新公用憑證指派給 Secure Sockets Layer (SSL) 接聽程式您的反向 proxy。 外部 （公用） 憑證要求的更新將會包含 lyncdiscover 主體替代名稱 (SAN) 項目。\<網域名稱\>。 然後您要修改外部 web 服務的現有接聽程式，或建立新的 web 發行規則的外部自動探索服務 URL，例如**lyncdiscover.contoso.com**。 如果您還沒有外部 Lync Server 2013 Web 服務 URL 的 web 發行規則的前端集區和 Director 集區 （如果您已部署 Director），您也需要為的發佈規則。

<div>


> [!NOTE]  
> 反向 Proxy 發行規則與接聽程式可服務外部 Web 服務及自動探索服務，只要指派給接聽程式的憑證包含兩服務之必要的主體名稱和主體替代名稱。 發行規則與網頁接聽程式的預設組態的詳細資訊，請參閱如需詳細資訊的<A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013 的反向 proxy 伺服器設定</A>。



</div>

如果您決定使用 HTTP 來進行初始自動探索服務要求，這樣就不需要為反向 Proxy 更新主體替代名稱，則您需要為連接埠 80 建立或修改 Web 發行規則。

本節中的程序說明如何在 Microsoft Forefront Threat Management Gateway 2010 中建立或修改 Web 發行規則，以進行自動探索。

<div>


> [!NOTE]  
> 這些程序假設您已安裝 Forefront Threat Management Gateway (TMG) 2010 Standard Edition。如果您使用其他的反向 Proxy，程序還是類似，但需要對應協力廠商產品的文件。



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>為外部自動探索 URL 建立 Web 發行規則

1.  按一下 **[開始]**，依序指向 **[程式集]** 和 **[Microsoft Forefront TMG]**，然後按一下 **[Forefront TMG 管理]**。

2.  在左邊的窗格，展開 [伺服器名稱]****，用滑鼠右鍵按一下 [防火牆原則]****，指向 [新增]****，然後按一下 [網站發行規則]****。

3.  在 [歡迎使用新增網頁發行規則]**** 頁面上，輸入新發行規則的顯示名稱 (例如 LyncDiscoveryURL)。

4.  在 [選取規則動作]**** 頁面上，按一下 [允許]****。

5.  在 [發行類型]**** 頁面上，選取 [發行單一網站或負載平衡器]****。

6.  在 [伺服器連線安全性]**** 頁面上，選取 [使用 SSL 連線到發行的 Web 伺服器或伺服器陣列]****。

7.  在 [**內部發行詳細資料**] 頁面上，在**內部網站名稱**] 中，輸入您的 Director 集區 (例如，lyncdir01.contoso.local) 的完整的網域名稱 (FQDN)。 如果您要建立規則的外部 Web 服務 URL 的前端集區上，輸入前端集區 (例如 lyncpool01.contoso.local) 的 FQDN。

8.  在 [**內部發行詳細資料**] 頁面的 [**路徑 （選用）**] 中，輸入**/** 表示要發佈、，然後選取 [**轉寄原始主機標頭**的資料夾路徑。

9.  在 [公用名稱詳細資料]**** 頁面上，執行下列作業：
    
      - 在 [為右列接受要求]**** 底下，選取 [這個網域名稱]****。
    
      - 在 [**公用名稱**] 中，輸入**lyncdiscover。**\<sipdomain\> (外部自動探索服務 URL)。 如果您要建立規則的外部 Web 服務 URL 的前端集區上，輸入 FQDN，針對您的前端集區 (例如 lyncwebextpool01.contoso.com) 上的外部 Web 服務。
    
      - 在 [**路徑**] 中，輸入**/**。

10. 在 [選取網頁接聽程式]**** 頁面上的 [網頁接聽程式]**** 中，選取具有更新公用憑證的現存 SSL 接聽程式。

11. 在 [驗證委派]**** 頁面上選取 [沒有委派，但用戶端可以直接驗證]****。

12. 在 [使用者組]**** 頁面上，選取 [所有使用者]****。

13. 在 [正在完成新網頁發行規則精靈]**** 頁面上，確認網頁發行規則設定正確，然後按一下 [完成]****。

14. 在網頁發行規則的 Forefront TMG 清單中，按兩下您剛才加入的新規則，以開啟 [內容]****。

15. 在 [到]**** 索引標籤中，執行下列作業：
    
      - 選取 [轉寄原始主機標頭而非實際標頭]****。
    
      - 選取 **[要求似乎來自 Forefront TMG 電腦]**。

16. 在 [橋接]**** 索引標籤中，設定下列項目：
    
      - 選取 [Web 伺服器]****。
    
      - 選取 [將要求重新導向至 HTTP 連接埠]****，並輸入 **8080** 作為連接埠號碼。
    
      - 選取 [將要求重新導向至 SSL 連接埠]****，並輸入 **4443** 作為連接埠號碼。

17. 按一下 [確定]****。

18. 按一下詳細資料窗格中的 **[套用]**，以儲存變更並更新設定。

19. 按一下 **[測試規則]**，以確認您的新規則設定正確。

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a>修改現有的 Web 發行規則以新增至外部自動探索 SAN 及 URL

1.  按一下 [開始]****，依序指向 [程式集]**** 和 [Microsoft Forefront TMG]****，然後按一下 [Forefront TMG 管理]****。
    
    <div>
    

    > [!IMPORTANT]  
    > 將為每個現有的發行規則及接聽程式重複此修改程序。 一般而言，這會是一個規則和接聽程式的前端集區和一個選用的 Director 或 Director 集區，如果您已部署它們。

    
    </div>

2.  在左窗格中，展開 **[伺服器名稱]**，在 **[防火牆原則]** 上按右鍵，按一下適用的規則。在 **[工作]** 索引標籤上，按一下 **[編輯選取的規則]**。

3.  在 **[公用名稱]** 索引標籤上的 **[此規則套用對象]** 中，選取 **[對下列網站的要求]**。

4.  按一下 **[新增]**，輸入新自動探索網站的名稱 (例如 "lyncdiscover.contoso.com")，然後按一下 **[確定]**。

5.  在 **[接聽程式]** 索引標籤上，按一下 **[選取憑證]** 並指派包含新增自動探索 SAN 項目的新憑證。關閉接聽程式與 Web 發行內容。

6.  按一下詳細資料窗格中的 [套用]****，以儲存變更並更新設定。

7.  按一下 [測試規則]****，以確認您的新規則設定正確。

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a>建立連接埠 80 的網頁發行規則

1.  按一下 **[開始]**，依序指向 **[程式集]** 和 **[Microsoft Forefront TMG]**，然後按一下 **[Forefront TMG 管理]**。

2.  在左邊的窗格，展開 [伺服器名稱]****，用滑鼠右鍵按一下 [防火牆原則]****，指向 [新增]****，然後按一下 [網站發行規則]****。

3.  在 [歡迎使用新增網頁發行規則]**** 頁面上，輸入新發行規則的顯示名稱 (例如 Lync Autodiscover (HTTP))。

4.  在 [選取規則動作]**** 頁面上，按一下 [允許]****。

5.  在 [發行類型]**** 頁面上，選取 [發行單一網站或負載平衡器]****。

6.  在 [伺服器連線安全性]**** 頁面上，選取 [使用不安全的連線以連線到發行的 Web 伺服器或伺服器陣列]****。

7.  在 [**內部發行詳細資料**] 頁面中，**內部網站名稱**] 中，輸入您的前端集區 (例如 lyncpool01.contoso.local) 內部 Web 服務 FQDN。

8.  在 [**內部發行詳細資料**] 頁面的 [**路徑 （選用）**] 中，輸入**/** 表示要發佈、，然後選取 [**轉寄原始主機標頭，而不是其中一個指定內部網站名稱] 欄位中**的資料夾路徑。

9.  在 [公用名稱詳細資料]**** 頁面上，執行下列作業：
    
      - 在 [為右列接受要求]**** 底下，選取 [這個網域名稱]****。
    
      - 在 [**公用名稱**] 中，輸入**lyncdiscover。**\<sipdomain\> (外部自動探索服務 URL)。
    
      - 在 [**路徑**] 中，輸入**/**。

10. 在 [選取網頁接聽程式]**** 頁面上的 [網頁接聽程式]**** 中，選取接聽程式，或是使用 [新增網頁接聽程式定義精靈] 來建立新的接聽程式。

11. 在 [驗證委派]**** 頁面上，選取 [沒有委派，用戶端無法直接驗證]****。

12. 在 [使用者組]**** 頁面上，選取 [所有使用者]****。

13. 在 [正在完成新網頁發行規則精靈]**** 頁面上，確認網頁發行規則設定正確，然後按一下 [完成]****。

14. 在網頁發行規則的 Forefront TMG 清單中，按兩下您剛才加入的新規則，以開啟 [內容]****。

15. 在 [橋接]**** 索引標籤中，設定下列項目：
    
      - 選取 [Web 伺服器]****。
    
      - 選取 [將要求重新導向至 HTTP 連接埠]****，並輸入 **8080** 作為連接埠號碼。
    
      - 確認未選取 [將要求重新導向至 SSL 連接埠]****。

16. 按一下 [確定]****。

17. 按一下詳細資料窗格中的 **[套用]**，以儲存變更並更新設定。

18. 按一下 **[測試規則]**，以確認您的新規則設定正確。

19. 確認外部自動探索服務 URL 未定義在任何其他網頁發行規則上。

</div>

<div>

## <a name="see-also"></a>另請參閱


[設定 Lync Server 2013 的反向 proxy 伺服器](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

