---
title: 使用反向 Proxy 伺服器發佈 Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f68ae51dba366282d7d3a5668b1358042a29917
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40973990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a>使用反向 proxy 伺服器在 Lync Server 2013 中發佈 Office Web Apps 伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-25_

如果您想要將外部使用者（也就是從組織外的防火牆以外的使用者登入），若要存取 Office Web Apps Server PowerPoint 簡報，您必須使用 Office Web Apps Server 和反向 proxy 伺服器（例如 Microsoft Forefront）。威脅管理閘道。 這也表示您將需要建立並設定網站發佈規則;該規則將協助確保使用者能夠連線到伺服器。 如果您不需要提供外部使用者的存取權，您就不需要設定網站發佈規則。

若要在 Forefront 威脅管理閘道設定網站發佈規則，請完成下列程式：

1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Forefront tmg**]，然後按一下 [ **Forefront tmg 管理**]。

2.  在 Forefront TMG，以滑鼠右鍵按一下 [**防火牆原則**]，指向 [**新增**]，然後按一下 [**網站發佈規則**]。

3.  在 [新增 Web 發佈規則嚮導] 的 [**歡迎使用新的 Web 發佈規則嚮導]** 頁面上，于 [ **Web 發佈規則名稱**] 方塊中輸入新規則的名稱（例如， **Office Web Apps Server 規則**），然後按 **[下一步]**。

4.  在 [**指定規則動作**] 頁面上，選取 [**允許**]，然後按一下 **[下一步]**。

5.  在 [**發佈類型**] 頁面上，選取 [**發佈單一網站或負載平衡器**]，然後按一下 **[下一步]**。

6.  在 [**伺服器連線安全性**] 頁面上，選取 [**使用 SSL 連線至已發佈的 Web 服務器或伺服器群]** ，然後按一下 **[下一步]**。

7.  在 [**內部發佈詳細資料**] 頁面的 [**內部網站名稱**] 方塊中，輸入您的 Office Web Apps 伺服器（例如， **officewebapps01.contoso.com**）的 FQDN，然後按 **[下一步]**。 在 [**內部網站名稱**] 方塊中輸入的名稱，必須出現在 [主旨] 欄位中，或是您已指派給 Office Web Apps 伺服器的憑證的 [消費者替換名稱] 欄位中。

8.  在 [**內部發佈詳細資料**] 頁面** / **上，輸入 [ **Path （選用）** ] 方塊，然後按一下 **[下一步]**。 /\*語法可協助確保網站的所有資料夾和子資料夾都已發佈。

9.  在 [**公用名稱詳細資料**] 頁面上，從 [**接受要求**] 下拉式清單中選取**此功能變數名稱（如下所示）** ，然後在 [公用名稱] 方塊中，輸入您的 Office Web Apps 伺服器的完整資格。 此名稱應該是用來存取您網站的名稱。 例如，如果您的網站是使用 URL http://officewebapps01.contoso.com來存取，則您應該在 [**公用名稱**] 方塊中輸入**officewebapps01.contoso.com** 。

10. 按一下 **[下一步]**。

11. 在 [**選取網頁攔截器]** 頁面上，按一下 [**新增**]。

12. 在 [新增 Web 攔截器定義嚮導] 的 [**網頁監聽器名稱**] 方塊中，輸入新網頁攔截器（例如， **SSL**）的名稱，然後按一下 **[下一步]**。

13. 在 [**用戶端連線安全性**] 頁面上，選取 [**與用戶端要求 SSL 安全**連線]，然後按 **[下一步]**

14. 在 [ **Web 攔截器 IP 位址]** 頁面上，選取 [**外部**]，選取 [**內部**]，然後按 **[下一步]**。

15. 在 [**偵聽程式 SSL 憑證]** 頁面上，選取 [**針對此網頁監聽程式使用單一憑證]** ，然後按一下 [**選取憑證**]。

16. 在 [**選取憑證**] 對話方塊中，選取要用於此網頁監聽程式的憑證，然後按一下 [**選取**]。

17. 在 [**偵聽程式 SSL 憑證]** 頁面上，按一下 **[下一步]**。

18. 在 [**驗證設定**] 頁面上，從 [**選取用戶端將認證給 Forefront TMG** ] 下拉式清單中選取 [**無驗證**]，然後按一下 **[下一步]**。

19. 在 [**單一登入設定**] 頁面上，按一下 **[下一步]**。

20. 在 [**完成新的 Web 攔截器嚮導]** 頁面上，查看您所做的配置選項摘要。 準備就緒時，按一下 **[完成]**。

21. 在 [**選取網頁攔截器]** 頁面上，按一下 **[下一步]**。

22. 在 [**驗證委派**] 頁面上，選取 [**無委派]，但用戶端可以直接**從 [**選取 Forefront TMG 使用的方法來驗證到已發佈的 Web 服務器**] 下拉式清單，然後按一下 **[下一步]**。

23. 在 [**使用者集**] 頁面上，確認已列出適當的使用者組。 根據預設，這是 [**所有使用者**] 設定。 按一下 [**新增**]，新增您可能已定義的其他使用者組。 完成時，請按 **[下一步]**。

24. 在 [**完成新的 Web 發佈規則嚮導]** 頁面上，按一下 **[完成]**。

請注意，按一下 **[完成]** 並不表示您已完成處理常式;也就是說，這不會自動套用並啟用新的規則。 相反地，您需要按一下將出現在 Forefront TMG 使用者介面中**的 [套用**] 按鈕。 當您按一下 [套用設定**變更描述**] 對話方塊**時，就**會出現此對話方塊。 按一下**該**對話方塊中的 [套用]，即可啟用新的發佈規則。

套用新規則之後，您必須對規則進行一些細微的修改，以確保使用者可以使用新的 PowerPoint 簡報功能。 若要這樣做，請完成下列程式：

1.  在 Forefront TMG，以滑鼠右鍵按一下新發佈規則的名稱，然後按一下 [**屬性**]。

2.  在 [**屬性**] 對話方塊中的 [**至**] 索引標籤上，選取 [**轉寄原始主機頭] （而非實際主機標頭**）。

3.  在 [**流量**] 索引標籤上，按一下 [**篩選**]，然後按一下 [**設定 HTTP**]。

4.  在 [設定**HTTP 原則規則**] 對話方塊中，清除 [**驗證正常化**] 核取方塊，然後按一下 **[確定]**。

5.  按一下 [**屬性**] 對話方塊中的 **[確定]**。

6.  在 Forefront TMG 中，**按一下 [** 套用] 以啟用變更。 當 [設定**變更變更描述**] 對話方塊出現時，**請按一下 [** 套用]。

完成安裝之後，您可以使用在[Lync Server 2013 中驗證 Office Web Apps server](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)設定主題中的程式，來測試您的 Office Web apps 伺服器。

</div>

<span> </span>

</div>

</div>

</div>

