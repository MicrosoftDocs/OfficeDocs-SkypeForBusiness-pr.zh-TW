---
title: Lync Server 2013：啟用或停用遠端使用者存取
description: Lync Server 2013：啟用或停用遠端使用者存取。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dea2d58c1978ac2d52365a4a453c40b38dd89c44
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547889"
---
# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中啟用或停用遠端使用者存取

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

遠端使用者是組織中具有持久 Active Directory 身分識別的使用者。 遠端使用者通常會在您的網路外登入 Lync Server，方法是在未連接到組織網路時，使用虛擬私人網路 (VPN) 。 遠端使用者包括在家中或在旅途中運作的員工，以及其他遠端工作者（如受信任的供應商，其已獲授與企業認證）。 如果您啟用遠端使用者的遠端使用者存取，支援的遠端使用者透過網際網路連線，而且不需要使用 VPN 連線，即可使用 Lync Server 與內部使用者共同作業。

若要支援遠端使用者存取，您必須啟用遠端使用者存取。 當您啟用遠端使用者存取時，您可以為整個組織啟用它。 如果您稍後想要暫時或永久防止遠端使用者存取，您可以為組織停用它。 使用本節中的程式來啟用或停用組織的遠端使用者存取。

<div>


> [!NOTE]  
> 啟用遠端使用者存取只會指定執行 Access Edge service 的伺服器可支援與遠端使用者的通訊，但遠端使用者無法參與立即訊息 (IM) 或組織中的會議，除非您也設定至少一個原則來管理遠端使用者存取的使用。 套用於一個原則層級的 Lync Server 原則設定可以覆寫在另一個原則層級套用的設定。 Lync Server 原則優先順序是：使用者原則 (最大的影響) 覆寫網站原則，然後網站原則會覆寫全域原則 (最小影響) 。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。 如需設定使用遠端使用者存取之原則的詳細資訊，請參閱 <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure 原則 to control remote user access In Lync Server 2013</A>。



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>啟用或停用組織的遠端使用者存取

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **同盟和外部存取**]，然後按一下 [ **Access Edge**設定]。

4.  在 [ **Access Edge** 設定] 頁面上，依序按一下 [ **全域**]、[ **編輯**]，然後按一下 [ **顯示詳細資料**]。

5.  在 [ **編輯 Access Edge**設定] 中，執行下列其中一項操作：
    
      - 若要啟用組織的遠端使用者存取，請選取 [ **啟用遠端使用者存取** ] 核取方塊。
    
      - 若要停用組織的遠端使用者存取，請清除 [ **啟用遠端使用者存取** ] 核取方塊。

6.  按一下 **[認可]**。

若要讓遠端使用者登入執行 Lync Server 的伺服器，您也必須至少設定一個外部存取原則，以支援遠端使用者存取。 如需詳細資訊，請參閱部署檔或作業檔中的 [設定原則，以控制 Lync Server 2013 中的遠端使用者存取](lync-server-2013-configure-policies-to-control-remote-user-access.md) 。

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用遠端使用者存取

您可以使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration Cmdlet 來管理遠端使用者存取。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-enable-remote-user-access"></a>啟用遠端使用者存取

  - 若要啟用遠端使用者存取，請將 **AllowOutsideUsers** 屬性的值設為 True ($True) ：
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>停用遠端使用者存取

  - 若要停用遠端使用者存取，請將 **AllowOutsideUsers** 屬性的值設為 False ($False) ：
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

