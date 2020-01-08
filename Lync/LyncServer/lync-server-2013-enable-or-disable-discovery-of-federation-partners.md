---
title: Lync Server 2013：啟用或停用探索同盟協力廠商
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e83f261fe6fa3ece259518b7730239adf20944c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a>在 Lync Server 2013 中啟用或停用探索同盟協力廠商

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

當您部署您的 Edge 伺服器並為貴組織啟用同盟時，您應該已指定是否支援聯盟夥伴網域的自動探索。 使用本主題中的程式來變更該設定。

<div>


> [!NOTE]  
> 下列程式假設您已經為您的組織啟用同盟。 如需啟用同盟的詳細資料，請參閱在部署檔或操作檔中<A href="lync-server-2013-enable-or-disable-remote-user-access.md">啟用或停用 Lync Server 2013 中的遠端使用者存取</A>。



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>若要啟用或停用貴組織的聯盟網域自動探索

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**存取邊緣**設定]。

4.  在 [**存取邊緣**設定] 頁面上，按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [**編輯存取邊緣**設定] 的 [**啟用與聯盟使用者的通訊**] 底下，選取或清除 [**啟用合作夥伴網域探索**] 核取方塊，以啟用或停用合作夥伴網域的自動探索。

6.  按一下 [認可]****。

若要讓聯盟使用者在 Lync Server 部署中與使用者共同作業，您也必須至少已設定一個外部存取原則來支援同盟使用者存取。 如需詳細資訊，請參閱在部署檔或操作檔中[啟用或停用 Lync Server 2013 中的同盟與公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線。 如需控制特定聯盟網域存取權的詳細資料，請參閱在 lync server [2013 中管理貴組織的 sip 聯盟網域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)、在[lync server 2013 中管理貴組織的 sip 同盟提供者](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)，以及在 Operations 檔中管理[LYNC server 2013 中的 XMPP 聯盟合作夥伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)。

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用同盟合作夥伴的探索

同盟合作夥伴的探索可以使用 Windows PowerShell 和 CsAccessEdgeConfiguration Cmdlet 進行管理。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-discovery-of-federation-partners"></a>若要啟用同盟合作夥伴的探索

  - 若要啟用同盟合作夥伴的發現，請將**EnablePartnerDiscovery**屬性的值設定為 True （$True）。 請注意，您必須啟用 DNS SRV 路由才能變更這個屬性值。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a>若要停用同盟合作夥伴的探索

  - 若要停用同盟合作夥伴的發現，請將**EnablePartnerDiscovery**屬性的值設定為 False （$False）：
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

