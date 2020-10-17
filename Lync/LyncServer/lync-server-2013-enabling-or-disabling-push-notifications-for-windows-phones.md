---
title: Lync Server 2013：啟用或停用 Windows 電話的推播通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for Windows Phones
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49733767
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4bcf8ccda422468416ae4c0b486e2e224b17f9f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515470"
---
# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a>啟用或停用 Lync Server 2013 中 Windows phone 的推播通知

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以將「徽章」、「圖示」或「警示」等的推播通知，傳送到 Windows Phone，即使行動應用程式不在使用中也是一樣。 推播通知會通知使用者有新的或錯過的 IM 邀請和語音信箱等事件。 您可以使用 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，啟用或停用 Windows Phone 裝置的推播通知。

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台啟用 Windows Phone 推播通知

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **推播通知** 設定] 瀏覽按鈕。

4.  在 [ **推入通知** 設定] 頁面上，按一下您要編輯的網站，然後按一下 [ **編輯** ] 功能表，再按一下 [ **顯示詳細資料**]。

5.  按一下 [ **啟用 Microsoft 推入通知** ] 核取方塊。

6.  按一下 **[認可]**。

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台停用 Windows Phone 的推播通知

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **推播通知** 設定] 瀏覽按鈕。

4.  在 [ **推入通知** 設定] 頁面上，按一下您要編輯的網站，然後按一下 [ **編輯** ] 功能表，再按一下 [ **顯示詳細資料**]。

5.  清除 [ **啟用 Microsoft 推入通知** ] 核取方塊。

6.  按一下 **[認可]**。

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用 Windows Phone 的推播通知

您可以使用 **Set-CsPushNotificationConfiguration** Cmdlet 來啟用或停用 Windows Phone 的推播通知。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a>啟用 Windows Phone 的推播通知

  - 若要啟用 Windows Phone 的推播通知，請將 EnableMicrosoftPushNotificationService 屬性的值設為 True ($True) 。 例如：
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a>停用 Windows Phone 的推播通知

  - 若要停用 Windows Phone 的推播通知，請將 EnableMicrosoftPushNotificationService 屬性的值設為 False ($False) 。 例如：
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

如需詳細資訊，請參閱 [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) Cmdlet 的 [說明] 主題。

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

