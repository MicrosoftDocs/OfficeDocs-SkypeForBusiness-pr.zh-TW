---
title: Lync Server 2013：啟用或停用 Iphone 的推播通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling push notifications for iPhones
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49733719
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ccd4e4c65c539f5a6af36d1012c32059b3e291a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a>啟用或停用 Lync Server 2013 中的 Iphone 推播通知

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以傳送徽章、圖示或警示等形式的推播通知，即使行動應用程式處於非使用中時也可以傳送到 iPhone。 推播通知會將事件（例如新的或未接的 IM 邀請及語音信箱）通知給使用者。 您可以使用 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面] 來啟用或停用 iPhone 版推播通知。

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 啟用 iPhone 版推播通知

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**推播通知**設定] 瀏覽按鈕。

4.  在 [**推播通知**設定] 頁面上，按一下您要編輯的網站，按一下 [**編輯**] 功能表，然後按一下 [**顯示詳細資料**]。

5.  按一下 [**啟用 Apple 推播通知**] 核取方塊。

6.  按一下 [認可]****。

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 停用 iPhone 版推播通知

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**推播通知**設定] 瀏覽按鈕。

4.  在 [**推播通知**設定] 頁面上，按一下您要編輯的網站，按一下 [**編輯**] 功能表，然後按一下 [**顯示詳細資料**]。

5.  清除 [**啟用 Apple 推播通知**] 核取方塊。

6.  按一下 [認可]****。

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用將推播通知到 iPhone

您可以使用**CsPushNotificationConfiguration** Cmdlet 來啟用或停用推播通知至 Apple iPhone。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-push-notifications-for-iphone"></a>啟用 iPhone 版推播通知

  - 若要啟用 iPhone 的推播通知，請將 EnableApplePushNotificationService 屬性的值設定為 True （$True）。 例如：
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a>停用 iPhone 版推播通知

  - 若要停用 iPhone 的推播通知，請將 EnableApplePushNotificationService 屬性的值設定為 False （$False）。 例如：
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

如需詳細資訊，請參閱[CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定推播通知](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

