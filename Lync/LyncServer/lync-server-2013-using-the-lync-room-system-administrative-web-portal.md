---
title: Lync Server 2013： 使用 Lync 會議室系統管理 Web 入口網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 759cae91575d3244d6860c6ec76fa664994d493e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>使用 Lync Server 2013 中的 Lync 會議室系統管理 Web 入口網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-11-10_

在伺服器上部署 LRS 之後，您可以藉由登入 LRS 管理入口網站從瀏覽器檢查所有 LRS 會議室的狀態。

<div>

## <a name="sign-in"></a>登入

1.  瀏覽至下列 URL:
    
    https://\<fe-server\>/lrs

2.  輸入 LRSSupport 帳戶或已新增至 LRSSupportAdminGroup 的 [安全性] 群組帳戶的認證。

![Lync 會議室系統管理員入口網站登入畫面](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 會議室系統管理員入口網站登入畫面")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>LRS 系統管理網站的入口網站摘要頁面

[摘要] 頁面上提供所有伺服器上部署 LRS 會議室的下列的資訊：

  - **標記**   自訂會議室可讓系統管理員的名稱。 標籤可以設定入口網站中，會議室名稱上按一下。

  - **健康情況**   會議室，衍生自會議室，會顯示在 [聊天室設定] 頁面的 [健康情況] 區段下方的彙總的健康狀態的健康狀態。

  - **接下來會議**   的日期和時間排定的下一個會議。

  - **LRS 版本，製造商、 模型**   這些值都會在 LRS 預先設定好。 根據製造商，這些欄位可能會留白。

  - **上次重新整理**   會顯示的上次在重新整理網頁。

![Lync 會議室系統系統管理入口網站摘要檢視](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync 會議室系統系統管理入口網站摘要檢視")

</div>

<div>

## <a name="lrs-room-information"></a>LRS 會議室的資訊

入口網站的 [會議室資訊] 區段可讓您檢視和設定個別 LRS 聊天室。 它包含四個區段： 設定、 詳細資料、 疑難排解和健康情況。

<div>

## <a name="settings"></a>設定

在 [設定] 區段中，您可以設定密碼會議室標記，預設磁碟區層級的會議室。 如果您設定這些設定，所做的變更會複寫只有在您重新啟動 LRS 主控台之後。 您只會看到 Lync 會議室系統所 15.12 和更新版本的版本的系統更新設定。

![Lync 會議室系統管理入口會議室設定](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync 會議室系統管理入口會議室設定")

</div>

<div>

## <a name="details"></a>詳細資料

[詳細資料] 區段中提供 LRS 會議室的設定，包括唯讀摘要： 上次重新整理; 的時間下一個會議;上次更新、 維護和校正;預設的喇叭、 麥克風，以及響鈴設定;版本;SIP URI;畫面及詳細資料每一個畫面中; 的數目狀態和活動。

![Lync 會議室系統系統管理入口網站詳細資料檢視](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync 會議室系統系統管理入口網站詳細資料檢視")

</div>

<div>

## <a name="troubleshooting"></a>疑難排解

[疑難排解] 區段可用來從遠端收集記錄，並將其儲存至指定的位置。 您也可以重新啟動 LRS 主控台 （LRS 使用者介面），或重新啟動整個系統。 若要收集記錄，提供指定之格式的資料夾路徑，並請確定在資料夾的寫入權限指定給 LRS 電腦帳戶。 記錄檔的大小過大時，可能需要 5 分鐘的時間來完成 [收集記錄檔。 重新整理] 頁面上，會提供最新狀態。

![Lync 會議室系統管理員入口網站的會議室記錄](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync 會議室系統管理員入口網站的會議室記錄")

</div>

<div>

## <a name="health"></a>醫療保健

[健康情況] 區段中提供 Lync Server 連線、 音訊裝置、 視訊裝置、 恢復能力的狀態，與螢幕裝置健全狀況的視覺的指示。

![Lync 會議室系統管理入口會議室健康狀況](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync 會議室系統管理入口會議室健康狀況")

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a>管理 Web 入口網站的其他備註

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>只有在 LRS 系統重新啟動之後，會套用設定變更。</P>
> <LI>
> <P>如果 LRSApp 帳戶密碼到期，您將無法查看會議室的狀態。 設定 LRSAppuser 帳戶密碼，讓它永遠不會到期，或請務必更新密碼時，它會接近到期日。</P>
> <LI>
> <P>內部部署只支援 LRS 管理 web 入口網站。</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>常見問題集

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>為什麼無法我登入系統管理 web 入口網站？

  - 當您開啟https://localhost/lrs，您將能夠看到登入] 頁面上，但當您輸入您的認證，您無法登入。 在此情況下，您必須開啟https://FQDNofFEserver/lrs來登入系統管理 web 入口網站。

  - 如果您在此存取管理 web 入口網站的電腦在工作群組，將無法運作 」 http:// 」。 請改用"https"。

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>為什麼在管理 web 入口網站中看不到 LRS？

  - 請確定您有 LRS 帳戶，您在部署中的，而且它們會建立根據 LRS 管理入口網站部署建議事項等。 請確定 LRS 帳戶佈建使用 Enable-csmeetingroom，未啟用 Get-csuser，Lync server 上。

  - 如果您已經建立 LRS 帳戶，而無法看到管理 web 入口網站中的帳戶，收集伺服器記錄檔與**MeetingPortal**元件選取，請使用 Lync Server 記錄工具，並再將它們傳送到您 LRS 支援連絡人。

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>為什麼無法看到 LRS 管理 web 入口網站中的狀態？

  - 請確定 LRSApp 使用者帳戶是已啟用 SIP 的。

  - 如果您仍然有問題，LRS 系統中收集**Trace.log**檔案從 d:\\追蹤\\LRSAdminLogs\\，然後將它傳送給您 LRS 支援連絡人。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

