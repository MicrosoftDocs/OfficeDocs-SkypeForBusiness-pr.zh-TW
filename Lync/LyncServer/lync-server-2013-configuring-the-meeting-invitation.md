---
title: Lync Server 2013：設定會議邀請
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bc948f81ddbc9bf4881b2188fc378315b3824ac
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532330"
---
# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a>在 Lync Server 2013 中設定會議邀請

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-16_

您可以在會議邀請的本文中包含下列選用專案，以自訂 Lync 2013 線上會議增益集所傳送的會議邀請：

  - **組織的標誌** 使用 [標誌 URL] 選項，將組織的標誌新增至會議邀請。 若會議邀請會傳送給組織外部的人員，該圖像應該位於公開提供的 URL。 支援的影像格式為 GIF 和 JPG。 雖然 Lync Server 2013 儲存的 URL 的圖像沒有大小限制，但為了獲得最佳結果，影像大小上限應為30圖元寬，188圖元寬。

  - **自訂的** [說明] 或 [支援] 連結新增組織的 [說明] 或 [支援小組] 網站的 URL。 若會議邀請會傳送給組織外部的人員，URL 應該是公開可用的。 最大 URL 長度為 1 KB。

  - **法律免責聲明文字** 新增要顯示在所有會議邀請中的法律文字或免責聲明的 URL。 若會議邀請會傳送給組織外部的人員，URL 應該是公開可用的。 最大 URL 長度為 1 KB。

  - **自訂頁腳文字** 新增將在邀請中呈現為自訂頁腳的文字。 可以新增的文字最大長度為 2 KB。

您可以使用 Lync Server 控制台或 Lync Server 管理命令介面來設定這些選項。

<div>


**使用 Lync Server 控制台自訂會議邀請**

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **會議** ]，然後按一下 [ **會議**設定]。

4.  在 [ **會議** 設定] 頁面上，按一下 [ **新增**]，然後執行下列其中一項動作：
    
      - 若要建立網站層級原則，請按一下 [ **網站**設定]。 在 [ **選取網站** ] 搜尋欄位中，輸入您要定義會議加入設定之網站的全部或部分名稱。 在產生的網站清單中，按一下您想要的網站，然後按一下 **[確定]**。
    
      - 若要建立集區層級原則，請按一下 [ **集**區設定]。 在 [ **選取服務** ] 搜尋欄位中，輸入您要定義會議加入設定之集區服務的全部或部分名稱。 在產生的服務清單中，按一下您想要的集區，然後按一下 **[確定]**。

5.  執行下列任一項作業：
    
      - 在 [ **徽標 URL** ] 欄位中，輸入您組織之標誌圖像的 URL。
    
      - 在 [說明 **URL** ] 欄位中，輸入您組織的 [說明] 或 [支援] 網站的 URL。
    
      - 在 [ **法律文字** ] 欄位中，輸入您要包含在會議邀請中之法律文字或免責聲明的 URL。
    
      - 在 [ **自訂頁腳] 文字** 欄位中，輸入尾行文字，最多 2 KB。

**使用 Lync Server 管理命令介面自訂會議邀請**

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 **New-CsMeetingConfiguration** 或 **Set-CsMeetingConfiguration** Cmdlet，以建立或設定會議邀請選項。 例如，執行：
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

