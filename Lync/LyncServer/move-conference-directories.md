---
title: 移動會議目錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ae7633d638571410c93cfefe87d9e333731a4bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>移動會議目錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

在解除池的授權前，您必須針對 Office 通訊伺服器 2007 R2 池中的每個會議目錄執行下列程式。

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>將會議目錄移至 Lync Server 2013

1.  開啟 Lync Server 管理命令介面。

2.  若要取得貴組織中會議目錄的身分識別，請執行下列命令：
    
        Get-CsConferenceDirectory
    
    由於這個 Cmdlet 會傳回貴組織中的所有會議目錄，因此您可能會想要將結果限制在您要解除授權的池中。 例如，如果您想要使用完整功能變數名稱（FQDN）來解除池中的 pool01.contoso.net：
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    這個 Cmdlet 會傳回服務識別碼包含 FQDN pool01.contoso.net 的所有會議目錄。

3.  若要移動會議目錄，請針對池中的每個會議目錄執行下列動作：
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    例如：
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> 您可能會遇到下列錯誤（如下所示），這是因為 Lync Server 管理命令介面需要來自 Active Directory 的更新組許可權。 若要解決錯誤，請關閉目前的視窗，然後開啟新的 Lync Server 管理命令介面，然後再次執行命令。



</div>

![Move-CsConferenceDirectory 錯誤輸出](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory 錯誤輸出")

</div>

</div>

<span> </span>

</div>

</div>

</div>

