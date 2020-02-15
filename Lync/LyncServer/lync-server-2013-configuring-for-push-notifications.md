---
title: Lync Server 2013： 設定推入通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f92ae27b919df6a32f06921df97746680a68b030
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>設定 Lync Server 2013 中的推入通知

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-12_

推入通知，形式的徽章、 圖示或提醒，可以傳送至行動裝置，只有非使用中的行動應用程式時，即使。 推入通知通知事件，例如新的或未接 IM 邀請與語音信箱的使用者。 Lync Server 2013 Mobility Service 將通知傳送至雲端式 Lync Server 推播通知服務，然後將通知傳送至 Apple 推播通知服務 (APNS) （適用於執行 Lync 2010 Mobile 用戶端 Apple 裝置） 其中或Microsoft 推播通知服務 (MPNS) （適用於執行 Lync 2010 Mobile 或 Lync 2013 行動用戶端的 Windows Phone 裝置）。

<div>


> [!IMPORTANT]  
> 如果您使用 Windows Phone 與 Lync 2010 Mobile 或 Lync 2013 行動用戶端，推播通知是很重要的考量。<BR>如果您在 Apple 裝置上使用 Lync 2010 Mobile，推播通知是很重要的考量。<BR>如果您在 Apple 裝置上使用 Lync 2013 行動，您不再需要推入通知。



</div>

設定您的拓撲支援推入通知，執行下列動作：

  - 如果您的環境具有 Lync Server 2010 或 Lync Server 2013 Edge Server，您需要新增新主機服務提供者，Microsoft Lync Online，然後再設定裝載提供者同盟組織與 Lync Online 之間。

  - 如果您的環境具有 Office Communications Server 2007 R2 Edge Server，您必須設定與 push.lync.com 的直接 SIP 同盟。
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com 是推入通知服務的 Microsoft Office 365 網域。

    
    </div>

  - 若要啟用推播通知，您需要執行**Set-cspushnotificationconfiguration** cmdlet。 根據預設，推入通知被關閉的。

  - 測試同盟設定和推入通知。

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>若要設定與 Lync Server 2013 或 Lync Server 2010 Edge Server 的推入通知

1.  登入 Lync Server 管理命令介面和 Ocscore 的 RtcUniversalServerAdmins 群組成員身分安裝所在的電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  新增 Lync Server 線上裝載提供者。 在命令列中輸入：
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    例如：
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > 您不能有一個以上的同盟關係與單一主機服務提供者。 也就是說，如果您已經設定裝載提供者已與 sipfed.online.lync.com 的同盟關係，請勿加上另一個主機服務提供者，即使裝載提供者的身分識別是 Nm-lynconline-w15-long 以外的項目。

    
    </div>

4.  設定裝載您的組織和推入通知服務在 Lync Online 之間的提供者同盟。 在命令列中輸入：
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>若要設定與 Office Communications Server 2007 R2 Edge Server 的推入通知

1.  使用 RtcUniversalServerAdmins 群組成員身分登入 Edge Server。

2.  按一下 [**開始]**[**所有程式]**、 [**系統管理工具**]，然後按一下 [**電腦管理]**。

3.  在主控台樹狀目錄中，展開 [**服務及應用程式**，以滑鼠右鍵按一下 [ **Microsoft Office Communications Server 2007 R2**，，然後按一下**屬性**。

4.  [**允許**] 索引標籤中，按一下 [**新增**]。

5.  在 [**新增同盟協力廠商**] 對話方塊中，執行下列動作：
    
      - 在 [**同盟協力廠商網域名稱**] 中，輸入**push.lync.com**。
    
      - 在 [**同盟協力廠商 Access Edge Server**，輸入**sipfed.online.lync.com**。
    
      - 按一下 [確定]****。

</div>

<div>

## <a name="to-enable-push-notifications"></a>若要啟用推入通知

1.  登入 Lync Server 管理命令介面和 Ocscore CsAdministrator 角色的成員身分安裝所在的電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  啟用推入通知。 在命令列中輸入：
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  啟用同盟。 在命令列中輸入：
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>測試同盟和推入通知

1.  登入 Lync Server 管理命令介面和 Ocscore CsAdministrator 角色的成員身分安裝所在的電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  測試同盟設定。 在命令列中輸入：
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    例如：
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  測試推入通知。 在命令列中輸入：
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    例如：
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a>請參閱


[Test-csfederatedpartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[Test-csmcxpushnotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

