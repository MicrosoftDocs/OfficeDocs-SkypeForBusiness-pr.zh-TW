---
title: Lync Server 2013：使用 Lync Room System 系統管理 Web 入口網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2369cdde9d14275fddf007b5e073c748ce5a8906
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>在 Lync Server 2013 中使用 Lync Room System 系統管理 Web 入口網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-11-10_

在伺服器上部署 LRS 之後，您可以從瀏覽器登入 LRS 管理網頁入口網站，查看所有 LRS 聊天室的狀態。

<div>

## <a name="sign-in"></a>登錄

1.  流覽至下列 URL：
    
    HTTPs://\<fe-伺服器\>/lrs

2.  輸入 LRSSupport 帳戶的認證，或是已新增至 LRSSupportAdminGroup 安全性群組的帳戶。

![Lync 會議室系統管理入口網站登入螢幕](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 會議室系統管理入口網站登入畫面")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>LRS 系統管理網頁入口網站摘要頁面

[摘要] 頁面提供伺服器上部署之所有 LRS 聊天室的下列資訊：

  - **標記**   管理員提供給聊天室的自訂名稱。 您可以按一下房間名稱，在入口網站中設定標籤。

  - **健康情況**   的健康情況，該房間是從聊天室的 [健康情況] 區段（在 [會議室設定] 頁面的 [健康情況] 區段中所示）衍生而來。

  - **[下一步會議**   ] 在排程下次會議的日期和時間。

  - **LRS 版本、製造商、型號**   這些值是在 LRS 中預先設定。 視製造商而定，這些欄位可能會保留空白。

  - **[上次**   重新整理] 會顯示最後一次重新整理網頁的時間。

![Lync 會議室系統管理入口網站摘要查看](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync 會議室系統管理入口網站摘要視圖")

</div>

<div>

## <a name="lrs-room-information"></a>LRS 會議室資訊

入口網站的 [會議室資訊] 區段可讓您查看和設定個別的 LRS 會議室。 它包含四個區段：設定、詳細資料、疑難排解及健康情況。

<div>

## <a name="settings"></a>設置

在 [設定] 區段中，您可以設定聊天室的密碼、房間標籤及預設音量等級。 如果您設定這些設定，變更只會在您重新開機 LRS 主控台後進行複製。 您只會看到版本15.12 及更新版本之 Lync 機房系統的系統更新設定。

![Lync 會議室系統管理入口網站室設定](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync 會議室系統管理入口網站室設定")

</div>

<div>

## <a name="details"></a>詳細資料

[詳細資料] 區段提供 LRS 會議室設定的唯讀摘要，包括：上次重新整理的時間;下次會議;上次更新、維護和校準;預設喇叭、麥克風和鈴聲設定;新版SIP URI;螢幕數目及每個畫面的詳細資料;狀態和活動。

![Lync 會議室系統管理入口網站詳細資料查看](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync 會議室系統管理入口網站詳細資料檢視")

</div>

<div>

## <a name="troubleshooting"></a>疑難排解

疑難排解一節可用來遠端收集記錄，並將它們儲存到指定的位置。 您也可以重新開機 LRS 主控台（LRS 使用者介面），或重新開機整個系統。 若要收集記錄，請以指定的格式提供資料夾路徑，並確認資料夾擁有 LRS 電腦帳戶的寫入權限。 如果記錄大小太大，可能需要最多5分鐘的時間來完成收集記錄。 重新整理頁面會提供最新狀態。

![Lync 會議室系統管理入口網站室記錄](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync 室系統管理員入口網站房間記錄")

</div>

<div>

## <a name="health"></a>運行

[健康情況] 區段提供 Lync Server 連線、音訊裝置、視頻裝置、復原狀態及螢幕裝置的健康情況的視覺指示。

![Lync 會議室系統管理入口網站室健康情況](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync 室系統管理員入口網站健康情況")

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a>有關系統管理網頁入口網站的其他注意事項

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>設定變更只會在 LRS 系統重新開機後套用。</P>
> <LI>
> <P>如果 LRSApp 帳戶密碼到期，您將無法看到聊天室的狀態。 設定 LRSAppuser 帳戶密碼，讓它永不過期，或者請務必在接近到期時更新密碼。</P>
> <LI>
> <P>僅限內部部署部署支援 LRS 系統管理網頁入口網站。</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>常見問題

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>為什麼我無法登入系統管理網頁入口網站？

  - 當您開啟https://localhost/lrs時，您可以看到 [登入] 頁面，但是當您輸入認證時，就無法登入。 在這種情況下，您https://FQDNofFEserver/lrs必須開啟，才能登入管理網頁入口網站。

  - 如果您要存取系統管理網頁入口網站的電腦位於 [工作組] 中，則 "HTTP://" 將無法運作。 請改用 "HTTPs"。

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>為什麼在管理網頁入口網站中看不到 LRS？

  - 請確定您在部署中有 LRS 帳戶，並根據 LRS 的系統管理網頁入口網站部署建議來建立它們。 在 Lync server 上，確認已使用 Enable-CsMeetingRoom （而非啟用-Move-csuser）來預配 LRS 帳戶。

  - 如果您已建立 LRS 帳戶，但在管理網頁入口網站中看不到帳戶，請使用已選取 [ **MeetingPortal** ] 元件的 Lync server 記錄工具收集伺服器記錄，然後將它們傳送到您的 LRS 支援連絡人。

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>為什麼在管理網頁入口網站中看不到 LRS 的狀態？

  - 確認 LRSApp 使用者帳戶已啟用 SIP。

  - 如果您仍有問題，請從 D：\\\\LRS 系統中收集\\ **Trace .log**檔案，並將它傳送到您的 LRS 支援連絡人。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

