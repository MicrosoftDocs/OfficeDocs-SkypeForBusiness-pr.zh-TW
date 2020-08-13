---
title: Lync Server 2013：啟用或停用同盟協力廠商的探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 893f61ce972ae85bcc88f47fe83c4fde220bb5c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a>在 Lync Server 2013 中啟用或停用同盟協力廠商的探索

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

當您部署 Edge Server 並為組織啟用同盟時，您應該會指定是否支援同盟協力廠商網域的自動探索。 使用本主題中的程式來變更該設定。

<div>


> [!NOTE]  
> 下列程式假設您已經為組織啟用同盟。 如需啟用同盟的詳細資訊，請參閱部署檔或作業檔中的 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">啟用或停用 Lync Server 2013 中的遠端使用者存取</A> 。



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>啟用或停用組織的自動探索同盟網域

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **外部使用者存取**]，然後按一下 [ **Access Edge**設定]。

4.  在 [ **Access Edge** 設定] 頁面上，依序按一下 [ **全域**]、[ **編輯**]，然後按一下 [ **顯示詳細資料**]。

5.  在 [ **編輯 Access Edge**設定] 的 [ **啟用與同盟使用者的通訊**] 下，選取或清除 [ **啟用夥伴網域探索** ] 核取方塊，以啟用或停用自動探索夥伴網域。

6.  按一下 **[認可]**。

若要讓同盟使用者與 Lync Server 部署中的使用者共同作業，您必須至少設定一個外部存取原則，以支援同盟使用者存取。 如需詳細資訊，請參閱部署檔或作業檔中的 [Enable 或 disable federation and PUBLIC IM connectivity In Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 。 如需控制特定同盟網域存取權的詳細資訊，請參閱在 lync server 2013 中管理組織的 [sip 同盟網域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)、 [在 lync server 2013 中管理組織的 sip 同盟提供者](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) ，以及在作業檔中 [管理 LYNC server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) 中的 XMPP 同盟合作夥伴。

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用同盟協力廠商的探索

同盟協力廠商的探索可使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration Cmdlet 來管理。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-enable-discovery-of-federation-partners"></a>啟用同盟協力廠商的探索

  - 若要啟用同盟協力廠商的探索，請將 **EnablePartnerDiscovery** 屬性的值設為 True ($True) 。 請注意，您必須啟用 DNS SRV 路由才能變更此屬性值。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a>停用同盟協力廠商的探索

  - 若要停用同盟協力廠商的探索，請將 **EnablePartnerDiscovery** 屬性的值設為 False ($False) ：
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

