---
title: 商務用 Skype Online 中的身分識別、範圍和承租人
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3e5217c4214e6e86ca4c1dff62410c247cf7f8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>商務用 Skype Online 中的身分識別、範圍和承租人

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-03-09_

許多用來管理商務用 Skype Online 的 Windows PowerShell Cmdlet，都需要您特別注意嘗試管理的專案。 例如，當您執行 CsUserAcp 指令[程式](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)時，您必須指出嘗試管理的使用者。 這會有意義。 除非您明確告訴 Cmdlet 要管理哪個使用者帳戶，否則**CsUserAcp 指令程式**不會知道應修改哪一個使用者的音訊會議資訊。 基於這個理由，每次執行 CsUserAcp 指令**程式**時，您必須加入 identity 參數，後面接著要修改的使用者帳戶身分識別：

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

如果字詞*識別碼*永遠稱為使用者帳戶的身分識別，將不會造成混淆的原因很小。 當您處理人員時（使用者、連絡人等等），身分識別會參照個別的使用者。 不過，使用者帳戶以外的專案也具有身分識別。 當您處理商務用 Skype Online 服務的元件時（原則、設定設定等等），「字詞身分識別」表示有些略有不同。 例如，請考慮下列命令：

    Get-CsMeetingConfiguration -Identity "global"

在此情況下，身分識別 "global" 是指會議配置設定的範圍。 *範圍*是用於商務用 Skype Online （在 Lync Server 中，也就是 Lync Server）中的字詞，用來指定的管理。 原則和設定預設會永遠具有全域範圍。 當您第一次設定商務用 Skype Online 帳戶時，預設會有一個全域原則和設定的集合，全域會議設定、全域外部存取原則、全域撥號對應表等的集合。

這些全域原則和設定會在 Microsoft Lync Server 2010 中引進，以協助確保所有使用者和所有元件都一定會受到管理。 在 Microsoft Office Communicator 2007 R2 中，這不一定是 true。 視您存取系統的方式而定，您可能會有很大的非管理狀態（通常是因為群組原則無法套用至您的使用者帳戶）。 相反地，在 Lync Server 和商務用 Skype Online 中，永遠不會留下任何專案。 這是因為絕對會強制執行全域原則及設定，而不是任何其他專案。

「代替其他任何人」是什麼意思？ 好的情況是，在商務用 Skype Online 中，您可以在*標記範圍*或管理的球體建立原則。 在標記範圍建立的原則（也稱為個別*使用者範圍*）優先于在全域範圍內建立的原則。 換句話說，每一使用者原則永遠優先于全域原則。 例如，您可能有兩個外部使用者存取原則。 全域原則禁止使用者與在公用立即訊息（IM）提供者（例如 Windows Live）上帳戶的使用者進行通訊。 每一使用者原則 AllowPublicIMCommunication，允許與公用 IM 提供者通訊。

您也可能會有兩位使用者： Ken Myer 和 Pilar Ackerman。 Ken Myer 已被指派每個使用者的原則。 尚未將每一使用者原則指派給 Pilar Ackerman;也就是說，她是由全域外部存取原則所管理。 下表顯示可與公用 IM 提供者通訊的使用者（如果有的話）：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>原則設定</th>
<th>Ken Myer</th>
<th>Pilar Ackerman</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>公用 IM 提供者的全域原則設定</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>公用 IM 提供者的每一使用者原則設定</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>使用者可以與公用 IM 提供者通訊</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>


如您所見，允許 Ken Myer 與公用 IM 提供者通訊。 這是因為指派給他的個別使用者原則中的設定會覆寫全域原則中的設定。 Pilar Ackerman 無法與公用 IM 提供者通訊。 這是因為她是由全域原則所管理，而全域原則則禁止這類通訊。

每個使用者的原則都必須為您建立 Microsoft 支援服務。 建立原則之後，您可以使用適當的**授與 Cs** Cmdlet 將它們指派給使用者（例如，[授與 get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)）。 因為原則識別永遠以標記**前置**詞開頭，所以個別使用者原則很容易識別。 例如：

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> 標記<STRONG>首碼</STRONG>日期回到 Lync Server 2010 的早期開發天。 在這天內，每個使用者的原則稱為<EM>標記原則</EM>，並由標記<STRONG>前置</STRONG>詞識別。 這些原則現在會以<EM>每個使用者的原則</EM>更準確地稱為，標籤範圍會更準確地稱為個別<EM>使用者範圍</EM>。 不過，由於技術原因，標記<STRONG>首碼</STRONG>永遠不會變更。



</div>

使用商務用 Skype Online 和 Windows PowerShell 的另一個關鍵術語是*租*使用者。 當您設定商務用 Skype Online 帳戶時，您的新部署會指派租使用者識別碼（GUID），這是類似以下的全域唯一識別碼（GUID）：

    bf19b7db-6960-41e5-a139-2aa373474354

在您每次執行 Cmdlet 時，有些商務用 Skype Online Cmdlet 會要求您輸入租使用者識別碼。 您必須輸入租使用者識別碼，即使您已登入，而且只有一個承租人。 幸運的是，您不需要記住租使用者識別碼。 您可以隨時執行下列 Windows PowerShell 命令，來取得租使用者識別碼：

    Get-CsTenant | Select-Object TenantId

當然，知道全域範圍和個別使用者範圍（或標記範圍）之間的差異，只是部分工作。 請務必知道何時（或甚至是）您可以使用這些範圍。 識別碼和租使用者參數也是如此。 下列主題說明不同的商務用 Skype Online Cmdlet 如何使用 identity、範圍及承租人參數：

  - [僅使用全域範圍之商務用 Skype Online 中的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [使用全域範圍及標記範圍的商務用 Skype Online 中的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [使用使用者身分識別的商務用 Skype Online 中的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [使用使用者身分識別及標記範圍的商務用 Skype Online 中的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [使用承租人參數的商務用 Skype Online 中的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [使用會議提供者身分識別的商務用 Skype Online 中的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [在商務用 Skype Online 中不使用範圍或身分識別的 Cmdlet](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

