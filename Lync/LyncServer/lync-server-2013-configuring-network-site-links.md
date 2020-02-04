---
title: Lync Server 2013：設定網路網站連結
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
ms.openlocfilehash: e379a8195dd0a50d97a514307ac594908be4736c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>在 Lync Server 2013 中設定網路網站連結

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

在呼叫許可控制（CAC）配置中，您可以建立網路間原則，以定義直接連結之網站之間的頻寬限制。 當網路網站共用直接連結時，音訊與視頻連線的頻寬限制可以在這兩個網站之間定義。 您無法使用 Lync Server [控制台] 來設定網路網站原則，只能使用 Lync Server 管理命令介面中的 Cmdlet 來執行此操作。 您可以從 Lync Server 管理命令介面建立、修改及移除網路網站連結（又稱為「網路間的網站」原則）。

<div>

## <a name="to-create-a-network-site-link"></a>建立網路網站連結

1.  登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元中，輸入下列命令，以取代有效的設定值：
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    這個範例會建立名為 Reno\_的新網路網站連結，以設定 Reno 與新的網路網站之間的頻寬限制。 在執行這個命令之前，必須已經存在網路網站和頻寬原則設定檔。

如需詳細的參數描述，請參閱 Lync Server 管理命令介面檔中的[新 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 。 若要取得可套用至 network site link 的頻寬原則配置檔案清單，請呼叫**CsNetworkBandwidthPolicyProfile** Cmdlet。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 。

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>修改網路網站連結

1.  登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  使用**CsNetworkInterSitePolicy** Cmdlet 來修改指定的網路網站連結的屬性。 您可以修改（或兩者）或連線的網站，也可以修改與連結相關聯的頻寬原則設定檔。 以下是修改名為 Reno\_的網站連結的頻寬原則設定檔範例：
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

如需詳細的參數描述，請參閱 Lync Server 管理命令介面檔中的[設定 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) 。

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>刪除網路網站連結

1.  登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  使用**CsNetworkInterSitePolicy** Cmdlet 來移除網路網站連結。 下列範例會刪除 Reno\_的 [上海網路] 網站連結：
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

如需詳細的參數描述，請參閱 Lync Server 管理命令介面檔中的[Remove CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) 。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中呼叫許可控制 Cmdlet](https://docs.microsoft.com/powershell/module/skype/)  


[新-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[移除-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

