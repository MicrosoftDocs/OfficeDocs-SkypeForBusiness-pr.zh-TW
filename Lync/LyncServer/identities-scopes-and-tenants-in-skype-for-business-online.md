---
title: 商務用 Skype Online 中的身分識別、範圍和租使用者
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b08c459f64a4655ebb4dc670255645f985452aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>商務用 Skype Online 中的身分識別、範圍和租使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-03-09_

許多用來管理商務用 Skype Online 的 Windows PowerShell Cmdlet，都需要您特別注意您嘗試管理的專案。 例如，當您執行[CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) Cmdlet 時，您必須指出您嘗試管理的使用者。 這麼做很有意義。 除非您特別告訴 Cmdlet 要管理哪個使用者帳戶，否則**CsUserAcp** Cmdlet 不會知道應該修改哪一個使用者的音訊會議資訊。 基於這個原因，每當您執行**CsUserAcp** Cmdlet 時，您都會需要加入身分識別參數，後面接著要修改的使用者帳戶身分識別：

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

如果「期限」總是參照使用者帳戶的*身分識別，* 就不會有混淆的原因。 當您處理人員時（使用者、連絡人等等），身分識別會參照個別使用者本身。 不過，使用者帳戶以外的專案也會有身分識別。 當您處理商務用 Skype Online 服務的元件時（[原則]、[設定] 設定等），這項身分識別代表的意義稍有不同。 例如，請考慮下列命令：

    Get-CsMeetingConfiguration -Identity "global"

在此情況下，身分識別 "global" 代表會議設定的範圍。 [*範圍*] 是在商務用 Skype Online （以及 Lync Server）中用來指定球體管理的詞彙。 根據預設，原則和設定總是擁有全域範圍。 當您第一次設定商務用 Skype Online 帳戶時，會根據預設，擁有全域原則與設定的集合： [全域會議設定]、[全域外部存取原則]、[全域撥號方案] 等等。

在 Microsoft Lync Server 2010 中引進了這些全域原則和設定，以協助確保所有使用者和所有元件都能以某種方式管理。 在 Microsoft Office Communicator 2007 R2 中，這不一定是正確的。 視您存取系統的方式而定，您可能會在基本不受管理的狀態（通常是因為群組原則無法套用到您的使用者帳戶）中結束。 相反地，在 Lync Server 和商務用 Skype Online 中，系統不會有任何未受管理的功能。 這是因為無論其他內容為何，全域原則和設定都將會強制執行。

我們的意思是 "代替其他內容？ 在商務用 Skype Online 的情況下，您可以在 [標籤*範圍*] 或 [管理] 球形建立原則。 在標籤範圍建立的原則（也稱為 *[每使用者範圍*]）優先于在全域範圍中建立的原則。 換句話說，每個使用者的原則將永遠優先于全域原則。 例如，您可能會有兩個外部使用者存取原則。 全域原則禁止使用者與在公用立即訊息（IM）提供者（例如 Windows Live）上擁有帳戶的人員進行通訊。 AllowPublicIMCommunication 的每個使用者原則都允許與公用 IM 提供者進行通訊。

您也可能有兩個使用者： Ken Myer 及 Pilar 方。 Ken Myer 已指派給每個使用者的原則。 Pilar 方尚未指派給每個使用者的原則;也就是說，她是由全域外部存取原則所管理。 下表顯示哪個使用者（如果有的話）可以與公用 IM 提供者通訊：


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
<th>Pilar 方</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>公用 IM 提供者的全域原則設定</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>公用 IM 提供者的每使用者原則設定</p></td>
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


如您所見，您可以使用 Ken Myer 來與公用 IM 提供者進行通訊。 這是因為指派給他的每個使用者原則中的設定會覆寫全域原則中的設定。 Pilar 方無法與公用 IM 提供者進行通訊。 這是因為她是由全域原則所管理，而且全域原則會禁止這類通訊。

必須由 Office 365 支援為您建立每個使用者的原則。 建立原則之後，您就可以使用適當的**授與 Cs** Cmdlet （例如，[授與 CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)）指派給使用者。 每個使用者的原則都容易辨識，因為原則身分識別會以標籤**首碼**為開頭。 例如：

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> 標記<STRONG>首碼</STRONG>日期回到 Lync Server 2010 的早期開發日。 在這些天數中，每個使用者的原則稱為<EM>標記原則</EM>，且是由標籤<STRONG>首碼</STRONG>所識別。 現在，這些原則會更精確地參照為<EM>每個使用者的原則</EM>，而標記範圍則更準確地稱為 [<EM>每使用者] 範圍</EM>。 不過，出於技術方面的原因，不會變更標記的<STRONG>首碼</STRONG>。



</div>

使用商務用 Skype Online 和 Windows PowerShell*時所使用的另*一個重要詞彙。 當您設定商務用 Skype Online 帳戶時，系統會指派新部署的租使用者識別碼編號，這是類似以下的全域唯一識別碼（GUID）：

    bf19b7db-6960-41e5-a139-2aa373474354

幾個商務用 Skype Online Cmdlet 需要您在執行 Cmdlet 時輸入租使用者識別碼。 您必須輸入租使用者識別碼，即使您已登入，且只有一個租使用者。 幸運的是，您不需要記住租使用者識別碼。 您可以執行下列 Windows PowerShell 命令，隨時取得您的租使用者識別碼：

    Get-CsTenant | Select-Object TenantId

當然，只要知道全域範圍與每個使用者範圍（或標籤範圍）之間的差異，就只需要一半的工作。 您也可以瞭解何時（或即使是您）使用這些範圍。 對於身分識別和租使用者參數，也是如此。 下列主題說明不同的商務用 Skype Online Cmdlet 如何使用身分識別、範圍和租使用者參數：

  - [商務用 Skype Online 的 Cmdlet 只使用全域範圍](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [商務用 Skype Online 中使用全域範圍和標籤範圍的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [商務用 Skype Online 中使用使用者身分識別的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [商務用 Skype Online 中使用使用者身分識別和標籤範圍的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [商務用 Skype Online 中使用租使用者參數的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [商務用 Skype Online 中使用會議提供者身分識別的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [商務用 Skype Online 中不使用範圍或身分識別的 Cmdlet](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

