---
title: 使用反向 proxy 伺服器發佈 Office Web Apps Server
description: 使用反向 proxy 伺服器發佈 Office Web Apps Server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 888399e315d90624ba41e23e173fa33813a92b43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571729"
---
# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a>使用反向 proxy 伺服器在 Lync Server 2013 中發佈 Office Web Apps Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-25_

如果要讓外部使用者 (亦即，從組織防火牆外部登入的使用者) 能夠存取 Office Web Apps Server PowerPoint 簡報，您需要使用 Office Web Apps Server 及反向 Proxy 伺服器，例如 Microsoft Forefront Threat Management Gateway。 這也表示您將需要建立及設定網站發行規則;該規則會協助確保使用者能夠連接到伺服器。 如果您不需要提供存取權給外部使用者，則不需要設定網站發行規則。

若要在 Forefront Threat Management Gateway 中設定網站發行規則，請完成下列程序：

1.  依序按一下 [開始]****、[所有程式]****、[Microsoft Forefront TMG]**** 及 [Forefront TMG 管理]****。

2.  在 Forefront TMG 中，用滑鼠右鍵按一下 [防火牆原則]****，指向 [新增]****，然後按一下 [網站發行規則]****。

3.  在 [新增網頁發行規則精靈] 中，於「歡迎使用新增網頁發行規則精靈」**** 頁面上的 [網頁發行規則名稱]**** 方塊中，輸入新規則的名稱 (例如，**Office Web Apps Server Rule**) ，然後按 [下一步]****。

4.  在「指定規則動作」**** 頁面上，選取 [允許]****，然後按 [下一步]****。

5.  在「發行類型」**** 頁面上，選取 [發行單一網站或負載平衡器]****，然後按 [下一步]****。

6.  在「伺服器連線安全性」**** 頁面上，選取 [使用 SSL 連線到發行的 Web 伺服器或伺服器陣列]****，然後按 [下一步]****。

7.  在「內部發行詳細資料」**** 頁面上的 [內部網站名稱]**** 方塊中，輸入 Office Web Apps 伺服器的 FQDN (例如，**officewebapps01.contoso.com**)，然後按 [下一步]****。在 [內部網站名稱]**** 方塊中輸入的名稱，必須出現在您指派給 Office Web Apps Server 之憑證的 [主體] 欄位或 [主體替代名稱] 欄位中。

8.  在 [ **內部發行詳細資料** ] 頁面上，輸入 **/\*** ** (選用) ** ] 方塊中的路徑，然後按 **[下一步]**。 / \* 語法會協助確保發佈網站的所有資料夾與子資料夾。

9.  在「公用名稱詳細資料」**** 頁面上，從 [為右列接受要求]**** 下拉式清單中選取 [這個網域名稱 (在下方鍵入)]****，然後在 [公用名稱] 方塊中輸入 Office Web Apps Server 的完整名稱。 此名稱應該是用來存取網站的名稱。 例如，如果您的網站是使用 URL 來存取，則 http://officewebapps01.contoso.com 您應該在 [**公用名稱**] 方塊中輸入**officewebapps01.contoso.com** 。

10. 按 [下一步]****。

11. 在「選取網頁接聽程式」**** 頁面上，按一下 [新增]****。

12. 在 [新增網頁接聽程式定義精靈] 的 [網頁接聽程式名稱]**** 方塊中，輸入新網頁接聽程式的名稱 (例如，**SSL**)，然後按 [下一步]****。

13. 在「用戶端連線安全性」**** 頁面上，選取 [需要與用戶端之間的 SSL 安全連線]****，然後按 [下一步]****。

14. 在「網頁接聽程式 IP 位址」**** 頁面上，選取 [外部]****，選取 [內部]****，然後按 [下一步]****。

15. 在「接聽程式 SSL 憑證」**** 頁面上，選取 [在這個網頁接聽程式使用單一憑證]**** ，然後按一下 [選取憑證]****。

16. 在 [選取憑證]**** 對話方塊中，選取要用於這個網頁接聽程式的憑證，然後按一下 [選取]****。

17. 在「接聽程式 SSL 憑證」**** 頁面上，按 [下一步]****。

18. 在「驗證設定」**** 頁面上，從 **[選取用戶端提供憑證給 Forefront TMG 的方式]** 下拉式清單中選取 [無驗證]****，然後按 [下一步]****。

19. 在「單一登入設定」**** 頁面上，按 [下一步]****。

20. 在「正在完成新網頁接聽程式精靈」**** 頁面上，檢閱您已選擇的設定摘要。準備好時，按一下 [完成]****。

21. 在「選取網頁接聽程式」**** 頁面上，按 [下一步]****。

22. 在「驗證委派」**** 頁面上，從 [選取 Forefront TMG 用來向發行的 Web 伺服器驗證的方法]**** 下拉式清單中選取 [沒有委派，但用戶端可以直接驗證]****，然後按 [下一步]****。

23. 在「使用者組」**** 頁面上，確認已列出適當的使用者組。依預設，這是 [所有使用者]**** 使用者組。按一下 [新增]****，以新增您已定義的其他使用者組。完成後按 [下一步]****。

24. 在「正在完成新增網頁發行規則精靈」**** 頁面上，按一下 [完成]****。

請注意，按一下 [完成]**** 並不表示您已完成程序；也就是說，這並不會自動套用或及啟用新規則。您必須按一下出現在 Forefront TMG 使用者介面中的 [套用]**** 按鈕。當您按一下 [套用]**** 時，會出現 [設定變更說明]**** 對話方塊。按一下該對話方塊中的 [套用]****，以啟用新的發行規則。

套用您的新規則之後，您將需要對規則進行一些次要修改，以確保使用者可以使用新的 PowerPoint 簡報功能。 若要執行這項作業，請完成下列程序：

1.  在 Forefront TMG 中，以滑鼠右鍵按一下新發行規則的名稱，然後按一下 [內容]****。

2.  在 [內容]**** 對話方塊中的 [到]**** 索引標籤上，選取 [轉寄原始主機標頭，而非實際標頭]****。

3.  在 [流量]**** 索引標籤上，按一下 [篩選]**** ，然後按一下 [設定 HTTP]****。

4.  在 [設定規則的 HTTP 原則]**** 對話方塊中，清除 [確認正規化]**** 核取方塊，然後按一下 [確定]****。

5.  在 [內容]**** 對話方塊中，按一下 [確定]****。

6.  在 Forefront TMG 中，按一下 [套用]****，以啟用變更。[設定變更說明]**** 對話方塊出現時，按一下 [套用]****。

完成安裝之後，您可以使用在 [Lync Server 2013 中驗證 Office Web Apps server](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)的主題中的程式，測試您的 Office Web apps server。

</div>

<span> </span>

</div>

</div>

</div>

