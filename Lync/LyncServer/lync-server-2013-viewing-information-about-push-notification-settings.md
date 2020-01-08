---
title: Lync Server 2013：查看推播通知設定的相關資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da9279d09ab3b344514a472f3fb0f38e7071aabd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a>在 Lync Server 2013 中查看推播通知設定的相關資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以傳送徽章、圖示或警示等形式的推播通知，即使行動應用程式處於非使用中時也能傳送給行動裝置。 推播通知會將事件（例如新的或未接的 IM 邀請及語音信箱）通知給使用者。 您可以使用 Lync Server 2013 的 [控制台] 或 [Lync Server 2013 管理命令介面]，查看行動裝置的資訊推播通知設定。

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a>從 Lync Server [控制台] 查看推播通知資訊

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**推播通知**設定] 瀏覽按鈕。

4.  在 [**推播通知**設定] 頁面上，按一下您要查看的網站，按一下 [**編輯**] 功能表，然後按一下 [**顯示詳細資料**]。

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看推播通知資訊

您可以使用 Windows PowerShell 和**CsPushNotificationConfiguration** Cmdlet 來查看推播通知設定設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-push-notification-configuration-information"></a>若要查看推播通知配置資訊

  - 若要查看所有推播通知設定的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsPushNotificationConfiguration
    
    這會傳回如下所示的資訊：
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

如需詳細資訊，請參閱[CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) Cmdlet 的說明主題。

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

