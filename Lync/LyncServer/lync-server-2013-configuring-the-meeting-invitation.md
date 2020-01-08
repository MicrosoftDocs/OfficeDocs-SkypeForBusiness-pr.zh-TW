---
title: Lync Server 2013：設定會議邀請
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 014a42597e3df416d9e502eaaa90e2f1e71e35ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a>在 Lync Server 2013 中設定會議邀請

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-16_

您可以透過在會議邀請內文中加入下列選用專案，來自訂 Lync 2013 線上會議增益集所傳送的會議邀請：

  - **貴組織的標誌**使用 [標誌 URL] 選項將貴組織的標誌新增至會議邀請。 如果會議邀請會傳送給您組織外部的人員，則該影像應該位於公開提供的 URL。 支援的影像格式為 GIF 和 JPG。 雖然 Lync Server 2013 儲存的 URL 在影像上沒有大小限制，但若要獲得最佳結果，影像的大小上限必須為30圖元，高為188圖元寬。

  - **自訂的**[說明] 或 [支援] 連結新增您組織的 [說明] 或 [支援小組] 網站的 URL。 如果會議邀請會傳送給您組織外部的人員，URL 應該是公開提供的。 最大 URL 長度為 1 KB。

  - **法律免責聲明文字**新增將在所有會議邀請中顯示之法律文字或免責聲明的 URL。 如果會議邀請會傳送給您組織外部的人員，URL 應該是公開提供的。 最大 URL 長度為 1 KB。

  - **自訂頁尾文字**新增將在邀請中呈現為自訂頁尾的文字。 可新增的文字最大長度為 2 KB。

您可以使用 Lync Server [控制台] 或 [Lync Server 管理命令介面] 來設定這些選項。

<div>


**使用 Lync Server [控制台] 自訂會議邀請**

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議配置**]。

4.  在 [**會議**設定] 頁面上，按一下 [**新增**]，然後執行下列其中一項操作：
    
      - 若要建立網站層級原則，按一下 [**網站**設定]。 在 [**選取網站**搜尋] 欄位中，輸入您要定義會議加入設定的網站名稱全部或部分名稱。 在產生的網站清單中，按一下您想要的網站，然後按一下 **[確定]**。
    
      - 若要建立池層級原則，請按一下 [**池**設定]。 在 [**選取服務**搜尋] 欄位中，輸入您要定義會議加入設定的全部或部分的 [池服務] 名稱。 在產生的服務清單中，按一下您想要的 [池]，然後按一下 **[確定]**。

5.  請執行下列任何一項操作：
    
      - 在 [**標誌 URL** ] 欄位中，輸入組織標誌影像的 URL。
    
      - 在 [說明**URL** ] 欄位中，輸入您組織的 [說明] 或 [支援] 網站的 URL。
    
      - 在 [**法律文字**] 欄位中，輸入您要包含在會議邀請中之法律文字或免責聲明的 URL。
    
      - 在 [**自訂頁尾文字**] 欄位中，輸入頁尾文字（最多 2 KB）。

**使用 Lync Server 管理命令介面來自訂會議邀請**

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行**新的 CsMeetingConfiguration**或 CsMeetingConfiguration Cmdlet 來建立或**設定**會議邀請選項。 例如，執行：
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

