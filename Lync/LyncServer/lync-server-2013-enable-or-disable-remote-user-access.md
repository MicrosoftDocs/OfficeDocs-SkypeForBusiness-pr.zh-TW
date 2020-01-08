---
title: Lync Server 2013：啟用或停用遠端使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a8edd8d6736d181b59579db29cc1e7244b0a750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中啟用或停用遠端使用者存取

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

遠端使用者是組織內擁有持久 Active Directory 身分識別的使用者。 當遠端使用者未連線到貴組織的網路時，使用虛擬私人網路（VPN）從網路外部登入 Lync Server。 遠端使用者包括在家中或在路上以及其他遠端工作人員（例如受信任的供應商，即已獲授與企業認證的人員）工作的員工。 如果您為遠端使用者啟用遠端使用者存取，支援的遠端使用者透過網際網路連線，而且不需要使用 VPN 連線，就能與使用 Lync Server 的內部使用者共同作業。

若要支援遠端使用者存取，您必須啟用遠端使用者存取。 當您啟用遠端使用者存取時，就會為您的整個組織啟用此許可權。 如果您稍後想要暫時或永久避免遠端使用者存取，您可以針對您的組織停用它。 使用本節中的程式來啟用或停用貴組織的遠端使用者存取權。

<div>


> [!NOTE]  
> 啟用遠端使用者存取只會指定執行 Access Edge 服務的伺服器支援與遠端使用者的通訊，但遠端使用者無法參與立即訊息（IM）或組織中的會議，除非您在此設定至少一個管理遠端使用者存取使用的原則。 在一個策略層級套用的 Lync Server 原則設定，可以覆寫在其他原則層級套用的設定。 Lync 伺服器策略優先順序為：使用者原則（最大影響）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。 這表示原則設定越接近策略設定的物件，就會受到對物件的影響。 如需有關設定遠端使用者存取的原則的詳細資訊，請參閱<A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">在 Lync Server 2013 中設定控制遠端使用者存取權的原則</A>。



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>若要啟用或停用貴組織的遠端使用者存取權

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**同盟與外部存取**]，然後按一下 [**存取邊緣**設定]。

4.  在 [**存取邊緣**設定] 頁面上，按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [**編輯存取邊緣**設定] 中，執行下列其中一項操作：
    
      - 若要為您的組織啟用遠端使用者存取，請選取 [**啟用遠端使用者存取權**] 核取方塊。
    
      - 若要停用您組織的遠端使用者存取權，請清除 [**啟用遠端使用者存取權**] 核取方塊。

6.  按一下 [認可]****。

若要讓遠端使用者登入您執行 Lync Server 的伺服器，您也必須至少將一個外部存取原則設定為支援遠端使用者存取。 如需詳細資訊，請參閱在部署檔或操作檔中，[設定控制在 Lync Server 2013 中遠端使用者存取權的原則](lync-server-2013-configure-policies-to-control-remote-user-access.md)。

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用遠端使用者存取

您可以使用 Windows PowerShell 和 CsAccessEdgeConfiguration Cmdlet 來管理遠端使用者存取。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-remote-user-access"></a>啟用遠端使用者存取

  - 若要啟用遠端使用者存取，請將**AllowOutsideUsers**屬性的值設定為 True （$True）：
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>若要停用遠端使用者存取

  - 若要停用遠端使用者存取，請將**AllowOutsideUsers**屬性的值設定為 False （$False）：
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

