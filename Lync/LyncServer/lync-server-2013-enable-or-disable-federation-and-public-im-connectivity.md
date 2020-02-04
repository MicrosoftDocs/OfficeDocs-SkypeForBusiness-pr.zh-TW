---
title: Lync Server 2013：啟用或停用同盟與公用 IM 連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edbf03ee2e2772e6df1425ffd666176c1947f0e4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a>在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-06-24_

必須具備同盟的支援，才能讓擁有受信任的客戶或合作夥伴組織帳戶的使用者，包括您所支援之公用立即訊息（IM）提供者的合作夥伴網域和使用者與您在其中的使用者共同作業。機構. 必須具備同盟，才能使用託管 Exchange 服務提供者來提供語音信箱給企業語音使用者，其信箱位於託管 Exchange 服務（例如 Microsoft Exchange Online）。 當您與這些外部網域建立信任關係時，您可以授權這些網域中的使用者存取您的部署並參與 Lync Server 通訊。 這個信任關係稱為聯合體，它與 Active Directory 信任關係無關，或不依賴。

若要支援受聯盟網域使用者的存取，您必須啟用同盟。 如果您為組織啟用同盟，您也必須指定是否要實施下列選項：

  - **[啟用合作夥伴網域探索**   ] 如果您啟用這個選項，Lync Server 會使用網域名稱系統（DNS）記錄來嘗試找出未列于 [允許的網域] 清單中的網域，自動評估已探索的同盟夥伴的傳入流量，以及限制或封鎖該流量（根據信任層級、流量數量及管理員設定）。 如果您沒有選取此選項，即會針對您在 [允許的網域] 清單中所包含的網域中的使用者啟用 [聯盟使用者存取]。 不論您是否選取此選項，您都可以指定要封鎖或允許的個別網域，包括限制對執行聯盟網域中之存取邊緣服務之特定伺服器的存取權。 如需控制聯盟網域存取權的詳細資料，請參閱[在 Lync Server 2013 中設定允許的外部網域支援](lync-server-2013-configure-support-for-allowed-external-domains.md)。

  - **將封存免責聲明傳送給聯盟**   夥伴將會傳送給聯盟夥伴，讓您的部署中的歸檔已就緒。 如果您支援與同盟夥伴網域進行外部通訊的存檔，您應該啟用 [封存放棄免責聲明通知]，警告合作夥伴他們的郵件正在封存。

如果您稍後想要暫時或永久避免受聯盟網域的使用者存取，您可以針對貴組織停用同盟。 您可以使用本節中的程式來啟用或停用貴組織的同盟使用者存取權，包括指定貴組織支援的適當聯盟選項。

<div>


> [!NOTE]  
> 為您的組織啟用同盟時，只會指定執行存取邊緣服務的伺服器支援路由到聯盟網域。 聯盟網域中的使用者無法參與您組織中的 IM 或會議，除非您也將至少一個策略設定為支援同盟使用者存取。 公用 IM 服務提供者的使用者無法在您的組織中參與 IM 或會議，除非您也將至少一個原則設定為支援公用 IM 連線。 Lync Server 無法使用託管 Exchange 服務來提供呼叫應答、Outlook 語音存取（包括語音信箱），或針對其信箱位於託管 Exchange 服務的使用者的自動助理服務，直到您設定託管的語音信箱原則為止提供路由資訊的。 如需有關設定與其他組織中聯盟網域之使用者通訊的原則的詳細資訊，請參閱在作業檔中<A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">管理您的組織在 Lync Server 2013 中的 SIP 聯盟網域</A>。 此外，如果您想要支援與 IM 服務提供者的使用者進行通訊，您必須設定支援它的原則，同時還要針對您想要支援的個別服務提供者設定支援。 如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">管理您的組織在 Lync Server 2013 中的 SIP 聯盟提供者</A>。 如需有關建立託管語音信箱原則的詳細資訊，請參閱在部署檔中<A href="lync-server-2013-manage-hosted-voice-mail-policies.md">管理 Lync Server 2013 中的託管語音信箱原則</A>。



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>若要啟用或停用貴組織的聯盟使用者存取權

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**存取邊緣**設定]。

4.  在 [**存取邊緣**設定] 頁面上，按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [**編輯存取邊緣**設定] 中，執行下列其中一項操作：
    
      - 若要為您的組織啟用聯盟使用者存取，請選取 [**啟用與同盟使用者的通訊**] 核取方塊。
    
      - 若要停用貴組織的聯盟使用者存取，請清除 [**啟用與同盟使用者的通訊**] 核取方塊。

6.  如果您選取 [**啟用與聯盟使用者的通訊**] 核取方塊，請執行下列動作：
    
    1.  如果您想要支援自動探索合作夥伴網域，請選取 [**啟用合作夥伴網域探索**] 核取方塊。
    
    2.  如果您的組織支援外部通訊的封存，請選取 [將封存**放棄免責聲明傳送給聯盟合作夥伴**] 核取方塊。

7.  按一下 [認可]****。

若要讓聯盟使用者在 Lync Server 2013 部署中與使用者共同作業，您也必須至少設定一個外部存取原則來支援同盟使用者存取。 如需詳細資訊，請參閱在部署檔或作業檔中，[設定在 Lync Server 2013 中控制聯盟使用者存取權的原則](lync-server-2013-configure-policies-to-control-federated-user-access.md)。 若要控制特定聯盟網域的存取權，請參閱在部署檔或操作檔中的[Lync Server 2013 中設定允許的外部網域支援](lync-server-2013-configure-support-for-allowed-external-domains.md)。

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 啟用或停用同盟與公用 IM 連線

您也可以使用 Windows PowerShell 和 CsAccessEdgeConfiguration Cmdlet 來管理同盟與公用 IM 連線。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a>啟用同盟與公用 IM 連線

  - 若要啟用同盟與公用 IM 連線，請將**AllowFederatedUsers**屬性的值設定為 True （$True）：
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a>停用同盟與公用 IM 連線

  - 若要停用同盟與公用 IM 連線，請將**AllowFederatedUsers**屬性的值設定為 False （$False）：
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

