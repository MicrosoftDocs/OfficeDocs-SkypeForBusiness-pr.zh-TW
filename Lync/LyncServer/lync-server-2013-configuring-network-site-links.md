---
title: Lync Server 2013：設定網路站台連結
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50457100f1ba476fd3ddfa923b73acd6bfe6d843
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>在 Lync Server 2013 中設定網路站台連結

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

在通話許可控制 (CAC) 組態中，您可以建立網路網站間原則以定義直接連結的網站之間的頻寬限制。 當網路網站共用直接連結時，您可以定義這兩個網站之間音訊與視訊連線的頻寬限制。 您無法使用 Lync Server 控制台設定網路網站原則，這只可以使用 Lync Server 管理命令介面中的 Cmdlet 進行。 您可以建立、修改及移除網路站台連結 (也稱為從 Lync Server 管理命令介面) 網路內部網站原則。

<div>

## <a name="to-create-a-network-site-link"></a>若要建立網路網站連結

1.  以[Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。

2.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元中輸入下列命令，其中的值換成您組態適用的有效值：
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    這個範例會建立名為雷諾的新網路站台連結 \_ ，此連結會設定雷諾和上點網路網站之間的頻寬限制。 網路網站與頻寬原則設定檔在執行此命令前即必須存在。

如需詳細的參數描述，請參閱 Lync Server 管理命令介面檔中的[CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 。 若要擷取可套用至網路網站連結之頻寬原則設定檔的清單，請呼叫 **Get-CsNetworkBandwidthPolicyProfile** Cmdlet。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 。

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>若要修改網路網站連結

1.  以[Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。

2.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  使用 **Set-CsNetworkInterSitePolicy** Cmdlet 來修改某個網路網站連結的內容。 您可以修改相連網站的其中一端網站 (或兩端網站都修改)，並且可以修改與連結相關聯的頻寬原則設定檔。 以下是修改名為雷諾上海之網站連結的頻寬原則設定檔的範例 \_ ：
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

如需詳細的參數描述，請參閱 Lync Server 管理命令介面檔中的[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) 。

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>若要刪除網路網站連結

1.  以[Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。

2.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  使用 **Remove-CsNetworkInterSitePolicy** Cmdlet 來移除網路網站連結。 下列範例會刪除雷諾 \_ 上海網路站台連結：
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

如需詳細的參數描述，請參閱 Lync Server 管理命令介面檔中的[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) 。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的通話許可控制 Cmdlet](https://docs.microsoft.com/powershell/module/skype/)  


[新 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

