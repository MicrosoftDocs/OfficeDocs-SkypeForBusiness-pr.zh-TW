---
title: 對照主要街道位址指南來測試市政位址
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfa4dd28ec05546366e029b6fb9fdf1c4b3ae310
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a>對照 Lync Server 2013 中的主要街道位址指南來測試市政位址

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>驗證排程</p></td>
<td><p>日常</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要許可權</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsRegistration Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

CsLisCivicAddress Cmdlet 可用來驗證新增至您的位置資訊服務（.LIS）資料庫的位置。 這個 Cmdlet 的運作方式是將位置與主要街道位址指南（MSAG）中的位置（屬於您的 E9-1-1 網路路由提供者）進行比較。 如果您沒有網路路由提供者或無法取得提供者，您的測試將會失敗。

如果您在命令中新增選用的切換參數 UpdateValidationStatus，則每個傳遞測試的位址都會將對應的 MSAGValid 資料庫屬性設定為 True。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsLisCivicAddress Cmdlet 可以用來測試個別的位址或測試多個位址。 例如，這個命令會測試位於雷蒙德、WA 中的單一位址：

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

根據比較，此命令會測試所有目前在您的 IIS 資料庫中的位址：

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

如需詳細資訊，請參閱[Test CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

測試 CsLisCivicAddress 會傳回提供的位址成功或失敗。 如果找不到位址，或無法連絡服務提供者，位址測試將會失敗。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsLisCivicAddress 可能失敗的一些常見原因：

  - IIS 服務提供者可能無法使用。 您可以執行 CsLisConfiguration Cmdlet，以取得您的 IIS 服務提供者 URL：
    
        Get-CsLisConfiguration 
    
    接著，您可以 ping 該 URL，以驗證服務提供者是否可供使用。

</div>

</div>

<span> </span>

</div>

</div>

</div>

