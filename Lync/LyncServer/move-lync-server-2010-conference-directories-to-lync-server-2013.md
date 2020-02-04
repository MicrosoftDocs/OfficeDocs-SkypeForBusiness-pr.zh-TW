---
title: 將 Lync Server 2010 會議目錄移至 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9bd597665f389c814fbdc8fe1745587fd3d1b3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>移動會議目錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-28_

在解除池的授權前，您必須針對 Lync Server 2010 池中的每個會議目錄執行下列程式。

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>將會議目錄移至 Lync Server 2013

1.  開啟 Lync Server 管理命令介面。

2.  若要取得貴組織中會議目錄的身分識別，請執行下列命令：
    
        Get-CsConferenceDirectory
    
    上述命令會傳回貴組織中的所有會議目錄。 因此，您可能會想要將結果限制在已解除授權的池中。 例如，如果您是使用完整的功能變數名稱（FQDN） pool01.contoso.net 來解除池，請使用此命令，將傳回的資料限制在該池中的會議目錄：
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    該命令只會傳回 ServiceID 屬性包含 FQDN pool01.contoso.net 的會議目錄。

3.  若要移動會議目錄，請針對池中的每個會議目錄執行下列命令：
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    例如，若要移動會議目錄3，請使用此命令，並將 Lync Server 2013 池指定為 TargetPool：
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    如果您想要移動一個資源池中的所有會議目錄，請使用類似下列的命令：
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

如需有關解除授權 Lync 2010 池的完整、逐步指示，請參閱檔「卸載 Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)Server 2010 並移除伺服器角色」（可供下載）。

移動會議目錄時，您可能會遇到下列錯誤：

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

當 Lync Server 管理命令介面需要更新的 Active Directory 許可權集才能完成工作時，通常會發生此錯誤。 若要解決此問題，請關閉目前的管理命令介面實例，然後開啟一個新的 Shell 實例，然後重新執行命令，以移動會議目錄。

</div>

</div>

<span> </span>

</div>

</div>

</div>

