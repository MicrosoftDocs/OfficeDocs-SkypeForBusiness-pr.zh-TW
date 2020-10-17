---
title: Lync Server 2013：設定推播通知
description: Lync Server 2013：設定推播通知。
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
ms.openlocfilehash: 24c22ff42f666add9eac4966134c88b9bf680046
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548329"
---
# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>在 Lync Server 2013 中設定推播通知

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-12_

即使當行動應用程式非使用中時，也可以將「徽章」、圖示或警示等推播通知傳送給行動裝置。 推播通知會通知使用者有新的或錯過的 IM 邀請和語音信箱等事件。 Lync Server 2013 行動性服務會將通知傳送至雲端型 Lync Server 推播通知服務，然後針對執行 lync 2010 行動用戶端) 或 Microsoft 推播通知服務，針對執行 Lync 2010 行動裝置或 Lync 2013 行動用戶端 (的 Windows Phone 裝置，將通知傳送給 Apple Push Notification Service (APNS)  (。

<div>


> [!IMPORTANT]  
> 如果您使用 Windows Phone 搭配 Lync 2010 行動裝置或 Lync 2013 行動用戶端，推播通知是一個重要的考慮。<BR>如果您在 Apple 裝置上使用 Lync 2010 Mobile，推播通知是一個重要的考慮。<BR>如果您在 Apple 裝置上使用 Lync 2013 行動裝置，則不再需要推播通知。



</div>

執行下列動作，將拓撲設定為支援推播通知：

  - 如果您的環境具有 Lync Server 2010 或 Lync Server 2013 Edge Server，您必須新增主機服務提供者（Microsoft Lync Online），然後在您的組織和 Lync Online 之間設定裝載提供者同盟。

  - 如果您的環境具有 Office 通訊伺服器 2007 R2 Edge Server，您必須設定與 push.lync.com 的直接 SIP 同盟。
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com 是推播通知服務的 Microsoft Office 365 網域。

    
    </div>

  - 若要啟用推播通知，您必須執行 **Set-CsPushNotificationConfiguration** Cmdlet。 依預設，推播通知會關閉。

  - 測試同盟設定和推播通知。

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>使用 Lync Server 2013 或 Lync Server 2010 Edge Server 設定推播通知

1.  登入 Lync Server 管理命令介面和 Ocscore.msi 已安裝成 RtcUniversalServerAdmins 群組成員的電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  新增 Lync Server online 主機服務提供者。 在命令列中輸入：
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    例如：
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > 您不能有一個以上的「裝載提供者」的同盟關係。 也就是說，如果您已設定與 sipfed.online.lync.com 具有同盟關聯的裝載提供者，請勿為其新增其他主機服務提供者，即使主機服務的身分識別是 Nm-lynconline-w15-long 以外的其他專案。

    
    </div>

4.  在 Lync Online 上設定組織與推播通知服務之間的裝載提供者同盟。 在命令列中輸入：
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>若要使用 Office 通訊伺服器 2007 R2 Edge Server 設定推播通知

1.  以 RtcUniversalServerAdmins 群組成員的身分登入 Edge Server。

2.  依序按一下 [ **開始**]、[ **所有程式**]、[系統管理 **工具**] 及 [ **電腦管理**]。

3.  在主控台樹中，展開 [**服務及應用程式**]，再以滑鼠**按右鍵 [** **Microsoft Office 通訊伺服器 2007 R2**]，然後按一下 [內容]。

4.  在 [ **允許** ] 索引標籤上，按一下 [ **新增**]。

5.  在 [ **新增同盟合作夥伴** ] 對話方塊中，執行下列動作：
    
      - 在 [同盟 **夥伴功能變數名稱**] 中，輸入 **push.lync.com**。
    
      - 在 [同盟 **Partner Access Edge Server**] 中，輸入 **sipfed.online.lync.com**。
    
      - 按一下 [確定]****。

</div>

<div>

## <a name="to-enable-push-notifications"></a>啟用推播通知

1.  登入 Lync Server 管理命令介面和 Ocscore.msi 已安裝為 CsAdministrator role 成員的電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  啟用推播通知。 在命令列中輸入：
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  啟用同盟。 在命令列中輸入：
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>測試同盟及推播通知

1.  登入 Lync Server 管理命令介面和 Ocscore.msi 已安裝為 CsAdministrator role 成員的電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

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


[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

