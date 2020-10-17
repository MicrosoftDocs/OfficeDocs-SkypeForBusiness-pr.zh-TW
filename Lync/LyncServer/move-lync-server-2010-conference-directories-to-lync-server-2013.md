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
ms.openlocfilehash: 6d1a080f7183bbab62cae679c911c76261694406
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500270"
---
# <a name="move-conference-directories"></a>移動會議目錄

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-28_

在解除委任集區之前，必須對 Lync Server 2010 集區中的每個會議目錄執行下列程式。

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>將會議目錄移至 Lync Server 2013

1.  開啟 Lync Server 管理命令介面。

2.  若要取得組織中會議目錄的身分識別，請執行下列命令：
    
        Get-CsConferenceDirectory
    
    上述命令會傳回組織中的所有會議目錄。 因此，您可能會想要將結果限制在解除委任的集區。 例如，如果您要將集區的完整功能變數名稱解除委任 (FQDN) pool01.contoso.net，請使用下列命令，將傳回的資料限制為該集區的會議目錄：
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    該命令只會傳回 ServiceID 屬性包含 FQDN pool01.contoso.net 的會議目錄。

3.  若要移動會議目錄，請針對集區中的每個會議目錄執行下列命令：
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    例如，若要移動會議目錄3，請使用此命令，將 Lync Server 2013 集區指定為 Microsoft.rtc.management.writableconfig.settings.watchernode.targetpool：
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    如果您想要移動集區上的所有會議目錄，請使用類似下列的命令：
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

請參閱檔「卸載 Microsoft Lync Server 2010 及移除伺服器角色」 (可從 [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)) 下載，以取得解除委任 Lync 2010 集區的完整、逐步指示。

移動會議目錄時，您可能會遇到下列錯誤：

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

當 Lync Server 管理命令介面需要更新的一組 Active Directory 許可權才能完成工作時，通常會發生此錯誤。 若要解決此問題，請關閉目前的管理命令介面實例，然後開啟命令介面的新實例，然後重新執行命令，以便移動會議目錄。

</div>

</div>

<span> </span>

</div>

</div>

</div>

