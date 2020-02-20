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
ms.openlocfilehash: eae2d3b588cafb09fd2eaea821b998b546fd0211
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>移動會議目錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-04_

之前解除委任集區，您必須針對 Office Communications Server 2007 R2 集區中每個會議目錄執行下列程序。

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>若要將會議目錄移至 Lync Server 2013

1.  開啟 Lync Server 管理命令介面。

2.  若要取得您的組織中會議目錄的身分識別，請執行下列命令：
    
        Get-CsConferenceDirectory
    
    由於此 Cmdlet 會傳回組織中的所有會議目錄，所以您可能會想要將結果僅限於您要解除委任的集區。例如，如果您想要解除委任完整網域名稱 (FQDN) 為 pool01.contoso.net 的集區：
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    此 Cmdlet 會傳回服務 ID 中包含 FQDN pool01.contoso.net 的所有會議目錄。

3.  若要移動會議目錄，請針對集區中的每個會議目錄執行下列程式碼：
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    例如：
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> 您可能會遇到錯誤，由所造成 Lync Server 管理命令介面需要更新的組從 Active Directory 的權限，如下所示。 若要解決此錯誤，關閉目前視窗和開啟新的 Lync Server 管理命令介面，並再次執行命令。



</div>

![Move-csconferencedirectory 錯誤輸出](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-csconferencedirectory 錯誤輸出")

</div>

</div>

<span> </span>

</div>

</div>

</div>

