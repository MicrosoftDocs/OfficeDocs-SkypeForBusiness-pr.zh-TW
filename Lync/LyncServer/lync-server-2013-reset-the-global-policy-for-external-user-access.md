---
title: Lync Server 2013：重設外部使用者存取的全域原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 971239018f3a8e1bcc92c036f50ed36616256ac7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中重設外部使用者存取的全域原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

您無法完全刪除全域原則。 在全域原則上使用 [**刪除**] 選項時，只會將全域原則重設為預設設定，而不包含任何外部使用者存取選項的支援。

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>將全域原則重設為預設設定

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**外部存取原則**]。

4.  在 [**外部存取原則**] 索引標籤上，按一下 [全域原則]，按一下 [**編輯**]，然後按一下 [**刪除**]。

5.  當系統提示您確認刪除時，請按一下 **[確定]**。 頁面頂端會出現一則訊息，通知您全域原則已重設。

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來重設全域外部存取原則

您可以使用 Windows PowerShell 和 CsExternalAccessPolicy Cmdlet 來重設全域外部存取原則。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從遠端會話 Windows PowerShell 執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-reset-the-global-external-access-policy"></a>若要重設全域外部存取原則

  - 這個命令會重定全域外部存取原則：
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

如需詳細資訊，請參閱[Remove CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

