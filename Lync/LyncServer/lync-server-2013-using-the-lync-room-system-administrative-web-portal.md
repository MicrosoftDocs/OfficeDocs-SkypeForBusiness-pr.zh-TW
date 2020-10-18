---
title: Lync Server 2013：使用 Lync 會議室系統管理 Web 入口網站
description: Lync Server 2013：使用 Lync 會議室系統管理 Web 入口網站。
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
ms.openlocfilehash: 28c29677080bf081eae0fa4227e4cb56ccac697b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579649"
---
# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>在 Lync Server 2013 中使用 Lync 會議室系統管理 Web 入口網站

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-11-10_

在伺服器上部署 LRS 之後，您可以在瀏覽器中登入 LRS 管理網頁入口網站，以檢查所有 LRS 聊天室的狀態。

<div>

## <a name="sign-in"></a>登入

1.  流覽至下列 URL:
    
    HTTPs:// \<fe-server\> /lrs

2.  輸入 LRSSupport 帳戶的認證，或已新增至 LRSSupportAdminGroup 安全性群組的帳戶。

![Lync 會議室系統管理入口網站登錄畫面](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 會議室系統管理入口網站登錄畫面")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>LRS 系統管理 Web 入口網站摘要頁面

[摘要] 頁面針對伺服器上部署的所有 LRS 聊天室，提供下列資訊：

  - **標記**    管理員提供給會議室的自訂名稱。 您可以在入口網站中，按一下會議室名稱以設定標記。

  - **健全狀況**    會議室的健全狀況狀態，它是由聊天室的合計健康狀態所組成，它會顯示在 [會議室設定] 頁面的 [健康情況] 區段下。

  - **下一個會議**    排定下一個會議的日期和時間。

  - **LRS Version，Manufacturer，Model**    這些值是預先設定的 LRS。 視製造商而定，這些欄位可能會保留空白。

  - **上次重新整理**    顯示重新整理網頁的最後時間。

![Lync 會議室系統管理員入口網站摘要視圖](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync 會議室系統管理員入口網站摘要視圖")

</div>

<div>

## <a name="lrs-room-information"></a>LRS 會議室資訊

入口網站的 [聊天室資訊] 區段可讓您查看及設定個別的 LRS 聊天室。 包含四個區段：設定、詳細資料、疑難排解及健康情況。

<div>

## <a name="settings"></a>設定

在 [設定] 區段中，您可以設定會議室的密碼、會議室標記和預設磁片區層級。 如果您設定這些設定，則只有在您重新開機 LRS 主控台之後才會複製變更。 您只會看到版本15.12 和更新版本的 Lync 會議室系統的系統更新設定。

![Lync 會議室系統管理入口網站室設定](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync 會議室系統管理入口網站室設定")

</div>

<div>

## <a name="details"></a>詳細資料

[詳細資料] 區段提供 LRS 會議室設定的唯讀摘要，包括：上次重新整理的時間;下一個會議;上次更新、維護和校準;預設的喇叭、mic 及鈴聲設定;版本SIP URI;每個畫面的畫面數目及詳細資料;狀態和活動。

![Lync 會議室系統管理員入口網站詳細資料檢視](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync 會議室系統管理員入口網站詳細資料檢視")

</div>

<div>

## <a name="troubleshooting"></a>疑難排解

疑難排解區段可用於遠端收集記錄，並將其儲存到指定的位置。 您也可以重新開機 LRS 主控台 (LRS 使用者介面) 或重新開機整個系統。 若要收集記錄檔，請提供指定格式的資料夾路徑，並確定資料夾具有 LRS 電腦帳戶的寫入權限。 如果記錄檔的大小過大，則最多可能需要5分鐘的時間來收集記錄檔。 重新整理頁面可提供您最新的狀態。

![Lync 會議室系統管理入口網站室記錄](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync 會議室系統管理入口網站室記錄")

</div>

<div>

## <a name="health"></a>健康情況

「狀況」區段提供 Lync Server 連線、音訊裝置、影片裝置、恢復狀態及螢幕裝置狀況的視覺指示。

![Lync 會議室系統管理入口網站室健康情況](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync 會議室系統管理入口網站室健康情況")

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a>關於系統管理 Web 入口網站的其他注意事項

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>只有在重新開機 LRS 系統之後，才會套用設定變更。</P>
> <LI>
> <P>如果 LRSApp 帳戶密碼到期，您就無法看到聊天室的狀態。 設定 LRSAppuser 帳戶密碼，使其永不到期，或務必在密碼即將到期時更新。</P>
> <LI>
> <P>僅限內部部署部署支援 LRS 系統管理 web 入口網站。</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>常見問題集

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>為什麼我無法登入管理網頁入口網站？

  - 當您開啟時 https://localhost/lrs ，您可以看到 [登入] 頁面，但是當您輸入您的認證時，您無法登入。 在此情況下，您必須先開啟 https://FQDNofFEserver/lrs 以登入管理 web 入口網站。

  - 如果您用來存取管理網頁入口網站的機器是在工作組中，則 "HTTP://" 將無法運作。 請改為使用「HTTPs」。

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>為什麼我無法在管理網頁入口網站中看到 LRS？

  - 請確定您的部署中有 LRS 帳戶，且這些帳戶是根據 LRS 系統管理 Web 入口網站部署建議所建立。 請確定已使用 Lync server 上的 Enable-CsMeetingRoom，而不是啟用-Get-csuser 來布建 LRS 帳戶。

  - 如果您已建立 LRS 帳戶，但在管理 web 入口網站中看不到帳戶，請使用 Lync Server 記錄工具（選取 [ **MeetingPortal** ] 元件）來收集伺服器記錄，然後將其傳送給 LRS 支援連絡人。

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>為什麼我無法在管理網頁入口網站中看到 LRS 的狀態？

  - 請確定 LRSApp 的使用者帳戶已 SIP-enabled。

  - 如果仍有問題，請從 D：追蹤 LRSAdminLogs 收集 LRS 系統中的 **Trace .log** 檔案 \\ \\ \\ ，然後將它傳送給 LRS 支援連絡人。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

