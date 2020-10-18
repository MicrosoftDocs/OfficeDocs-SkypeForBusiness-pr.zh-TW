---
title: Lync Server 2013：查看推播通知設定的資訊
description: Lync Server 2013：查看推播通知設定的相關資訊。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44ee876df341833c93e97fd16664940629754a6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580029"
---
# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a>在 Lync Server 2013 中查看推播通知設定的相關資訊

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

即使當行動應用程式非使用中時，也可以將「徽章」、圖示或警示等推播通知傳送給行動裝置。 推播通知會通知使用者有新的或錯過的 IM 邀請和語音信箱等事件。 您可以使用 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，查看行動裝置的資訊推播通知設定。

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a>從 Lync Server 控制台查看推播通知資訊

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **推播通知** 設定] 瀏覽按鈕。

4.  在 [ **推入通知** 設定] 頁面上，按一下您要查看的網站，然後按一下 [ **編輯** ] 功能表，再按一下 [ **顯示詳細資料**]。

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看推播通知資訊

您可以使用 Windows PowerShell 和 **Get-CsPushNotificationConfiguration** Cmdlet 來查看推播通知設定設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-view-push-notification-configuration-information"></a>若要查看推播通知設定資訊

  - 若要查看所有推播通知設定設定的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsPushNotificationConfiguration
    
    如此將傳回類似如下的資訊：
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

如需詳細資訊，請參閱 [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) Cmdlet 的 [說明] 主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定推播通知](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

