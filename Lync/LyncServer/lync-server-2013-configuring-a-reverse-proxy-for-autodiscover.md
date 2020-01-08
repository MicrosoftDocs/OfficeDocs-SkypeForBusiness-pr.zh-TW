---
title: Lync Server 2013：針對自動探索設定反向 proxy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5445a9ce81835863b610ef32ecc51ccac5331c3f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a>在 Lync Server 2013 中針對自動探索設定反向 proxy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-12_

使用自動探索的用戶端自動探索和支援，需要修改現有的 web 發佈規則，或為反向 proxy 建立新的 web 發佈規則。 新發佈規則的修改或建立不依賴于決定是否要更新，或無法更新反向 proxy 憑證上的消費者備用名稱清單。

如果您決定在初始的 Lync Server 2013 自動探索服務要求中使用 HTTPS，並更新反向 proxy 憑證上的消費者備用名稱清單，您必須將更新的公用憑證指派給安全通訊端層（SSL）偵聽程式（在您的反向 proxy。 外部（公開）證書所需的更新將包含 lyncdiscover 的 [subject 替換名稱（SAN）] 專案。\<網功能變數名稱\>。 接著，您需要修改外部 web 服務的現有偵聽程式，或為外部自動探索服務 URL 建立新的 web 發佈規則，例如**lyncdiscover.contoso.com**。 如果您還沒有適用于前臺伺服器與主管池的外部 Lync Server 2013 Web Services URL 的 web 發佈規則（如果您已部署控制器），您也必須發佈規則。

<div>


> [!NOTE]  
> 只要指派給監聽器的憑證包含這兩者所需的消費者名稱和消費者替換名稱，反向 proxy 發佈規則及監聽器就可以同時為外部 web 服務和自動探索服務提供服務。 如需有關網頁監聽器與發佈規則預設設定的詳細資料，請參閱<A href="lync-server-2013-setting-up-reverse-proxy-servers.md">設定 Lync Server 2013 的反向 proxy 伺服器</A>以取得詳細資料。



</div>

如果您決定將 HTTP 用於初始自動探索服務要求，因此您不需要更新反向 proxy 的消費者備用名稱，您必須建立或修改埠80的 web 發佈規則。

本節中的程式說明如何在 Microsoft Forefront 威脅管理閘道2010中建立或修改 web 發佈規則，以進行自動探索。

<div>


> [!NOTE]  
> 這些程式假設您已安裝標準版的 Forefront 威脅管理閘道（TMG）2010。 如果您使用的是其他反向 proxy，程式會類似，但需要對應至協力廠商產品的檔。



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>建立外部自動探索 URL 的 web 發佈規則

1.  按一下 [**開始**]，指向 [**程式**]，指向 [ **Microsoft Forefront tmg**]，然後按一下 [ **Forefront TMG 管理**]。

2.  在左窗格中，展開 [**伺服器名稱**]，以滑鼠右鍵按一下 [**防火牆原則**]，指向 [**新增**]，然後按一下 [**網站發佈規則**]。

3.  在 [**歡迎使用新的 Web 發佈規則**] 頁面上，輸入新發佈規則的顯示名稱（例如，LyncDiscoveryURL）。

4.  在 [**選取規則動作**] 頁面上，選取 [**允許**]。

5.  在 [**發佈類型**] 頁面上，選取 [**發佈單一網站或負載平衡器**]。

6.  在 [**伺服器連線安全性**] 頁面上，選取 [**使用 SSL 連線至已發佈的 Web 服務器或伺服器**伺服器陣列]。

7.  在 [**內部發佈詳細資料**] 頁面的 [**內部網站名稱**] 中，輸入您的主管池（例如 lyncdir01）的完整功能變數名稱（FQDN）。 如果您是在 [前端] 池中為 [外部 Web 服務] URL 建立規則，請輸入前端池的 FQDN （例如，lyncpool01）。

8.  在 [**內部發佈詳細資料**] 頁面的 **[Path （選用）**] 中，輸入** / **要發行之資料夾的路徑，然後選取 **[轉寄原始主機標頭**]。

9.  在 [**公用名稱詳細資料**] 頁面上，執行下列動作：
    
      - 在 [**接受要求**] 下，選取 [**此功能變數名稱**]。
    
      - 在 [**公用名稱**] 中，輸入**lyncdiscover。**\<sipdomain\> （外部自動探索服務 URL）。 如果您是在 [前端] 池中為 [外部 Web 服務] URL 建立規則，請在您的前端池中輸入外部 Web 服務的 FQDN （例如，lyncwebextpool01.contoso.com）。
    
      - 在 [ **Path**] ** /** 中，輸入。

10. 在 [**選取網頁偵聽**程式] 頁面上的 [**網頁監聽器]** 中，選取您的現有 SSL 偵聽程式及已更新的公用證書。

11. 在 [**驗證委派**] 頁面上，選取 [**無委派]，但用戶端可以直接驗證**。

12. 在 [**使用者組**] 頁面上，選取 [**所有使用者**]。

13. 在 [**完成新的 Web 發佈規則嚮導]** 頁面上，確認 Web 發佈規則設定正確無誤，然後按一下 **[完成]**。

14. 在 web 發佈規則的 Forefront TMG 清單中，按兩下您剛剛新增的新規則，以開啟 [**屬性**]。

15. 在 [**至**] 索引標籤上，執行下列動作：
    
      - 選取 **[轉寄原始主機標頭，而不是實際主機**名]。
    
      - 選取**要求會顯示為來自 FOREFRONT TMG 電腦**。

16. 在 [**橋接**] 索引標籤上，設定下列專案：
    
      - 選取 [ **Web 服務器**]。
    
      - 選取 [**將要求重新導向至 HTTP 埠**]，然後輸入**8080**作為埠號碼。
    
      - 選取 [重新**導向 SSL 埠**]，然後輸入**4443**作為埠號碼。

17. 按一下 [確定]****。

18. 按一下 [詳細資料] 窗格**中的 [** 套用]，儲存變更並更新配置。

19. 按一下 [**測試規則**]，確認您的新規則設定正確。

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a>修改現有的 web 發佈規則，以新增外部自動探索 SAN 和 URL

1.  按一下 [**開始**]，指向 [**程式**]，指向 [ **Microsoft Forefront tmg**]，然後按一下 [ **Forefront TMG 管理**]。
    
    <div>
    

    > [!IMPORTANT]  
    > 您將針對您擁有的每個發佈規則和偵聽程式重複進行修改。 通常，這會是前端池的一個規則和偵聽程式，另一個則是用於選用的控制器或控制器池（如果您已部署）。

    
    </div>

2.  在左窗格中，展開 [**伺服器名稱**]，以滑鼠右鍵按一下 [**防火牆原則**]，然後按一下適用的規則。 按一下 [**任務**] 索引標籤上的 [**編輯選取的規則**]。

3.  在 [**公用名稱**] 索引標籤的 [**此規則適用**于] 中，選取下列網站的**要求**。

4.  按一下 **[新增]**，輸入新的自動探索網站名稱（例如，"lyncdiscover.contoso.com"），然後按一下 **[確定]**。

5.  在 [**攔截器**] 索引標籤上，按一下 [**選取憑證**]，然後將新憑證指派給已新增的自動探索 SAN 專案。 關閉 [監聽器] 和 [Web 發佈] 屬性。

6.  按一下 [詳細資料] 窗格**中的 [** 套用]，儲存變更並更新配置。

7.  按一下 [**測試規則**]，確認您的新規則設定正確。

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a>建立埠80的網路發佈規則

1.  按一下 [**開始**]，指向 [**程式**]，指向 [ **Microsoft Forefront tmg**]，然後按一下 [ **Forefront TMG 管理**]。

2.  在左窗格中，展開 [**伺服器名稱**]，以滑鼠右鍵按一下 [**防火牆原則**]，指向 [**新增**]，然後按一下 [**網站發佈規則**]。

3.  在 [**歡迎使用新的 Web 發佈規則**] 頁面上，輸入新發佈規則的顯示名稱（例如 [Lync 自動探索（HTTP）]）。

4.  在 [**選取規則動作**] 頁面上，選取 [**允許**]。

5.  在 [**發佈類型**] 頁面上，選取 [**發佈單一網站或負載平衡器**]。

6.  在 [**伺服器連線安全性**] 頁面上，選取 [**使用非安全連線來連線至已發佈的 Web 服務器或伺服器**伺服器陣列]。

7.  在 [**內部發佈詳細資料**] 頁面的 [**內部網站名稱**] 中，輸入您的前端池（例如，Lyncpool01）內部 Web 服務 FQDN。

8.  在 [**內部發佈詳細資料**] 頁面的 **[Path （選用）**] 中，輸入** / **要發行之資料夾的路徑，然後選取 **[轉寄原始主機標頭]，而不是在 [內部網站名稱] 欄位中指定的主機名稱**。

9.  在 [**公用名稱詳細資料**] 頁面上，執行下列動作：
    
      - 在 [**接受要求**] 下，選取 [**此功能變數名稱**]。
    
      - 在 [**公用名稱**] 中，輸入**lyncdiscover。**\<sipdomain\> （外部自動探索服務 URL）。
    
      - 在 [ **Path**] ** /** 中，輸入。

10. 在 [**選取 Web 攔截器]** 頁面上的 [**網頁偵聽**程式] 中，選取網頁監聽程式，或使用新的 web 攔截器定義嚮導來建立新的。

11. 在 [**驗證委派**] 頁面上，選取 [**無委派]，而且用戶端無法直接驗證**。

12. 在 [**使用者組**] 頁面上，選取 [**所有使用者**]。

13. 在 [**完成新的 Web 發佈規則嚮導]** 頁面上，確認 Web 發佈規則設定正確無誤，然後按一下 **[完成]**。

14. 在 web 發佈規則的 Forefront TMG 清單中，按兩下您剛剛新增的新規則，以開啟 [**屬性**]。

15. 在 [**橋接**] 索引標籤上，設定下列專案：
    
      - 選取 [ **Web 服務器**]。
    
      - 選取 [**將要求重新導向至 HTTP 埠**]，然後輸入**8080**作為埠號碼。
    
      - 確認沒有選取 [重新**導向 SSL 埠的重新導向要求**]。

16. 按一下 [確定]****。

17. 按一下 [詳細資料] 窗格**中的 [** 套用]，儲存變更並更新配置。

18. 按一下 [**測試規則**]，確認您的新規則設定正確。

19. 確認未在任何其他 web 發佈規則上定義外部自動探索服務 URL。

</div>

<div>

## <a name="see-also"></a>請參閱


[設定 Lync Server 2013 的反向 Proxy 伺服器](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

