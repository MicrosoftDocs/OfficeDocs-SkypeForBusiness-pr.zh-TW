---
title: 身分識別、 範圍與 skype for Business Online 租用戶
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
ms.openlocfilehash: e6c6f0c08d03cd746f5929f6a7f1d82373a527a4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>身分識別、 範圍與 skype for Business Online 租用戶

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015年-03-09_

許多用來管理商務用 Skype 的 Windows PowerShell cmdlet 需要非常特定的對想要管理的項目。 例如，當您執行[設定 CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)指令程式，您必須指定想要管理的使用者。 這是合理。 除非您特別告知指令程式來管理使用者帳戶，**設定 CsUserAcp**指令程式都有任何想法應該可以修改哪些使用者的音訊會議資訊。 基於這個理由，每次您執行**設定 CsUserAcp** cmdlet 時，您將需要加入 Identity 參數，後面接著要修改的使用者帳戶的身分識別：

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

如果字詞一律參照的使用者帳戶的身分識別*身分識別*，就很少造成混淆。 當您正在處理與人員 （使用者、 連絡人、 等等） 時，身分識別參照個別的使用者本身。 不過，使用者帳戶以外的項目也有身分識別。 當您在處理與 Skype for Business Online service 的元件-原則、 組態設定，等等 — 身分識別 」 是指稍有不同的字詞。 例如，假設此命令：

    Get-CsMeetingConfiguration -Identity "global"

在此情況下，Identity 為"global 」 指的是範圍的會議組態設定。 *範圍*是和所用的商務用 Skype （Lync Server） 的字詞來指定鄰的管理。 根據預設，原則與設定一律會擁有全域範圍。 當您第一次設定您 Skype for Business Online 帳戶必須，根據預設，全域原則及設定一群 — 全域會議組態設定、 全域外部存取原則、 全域撥號對應表，依此類推。

為了協助確保之所有使用者和所有元件會永遠，以某種方式，受管理的 Microsoft Lync Server 2010 中引進下列全域原則與設定。 這是不一定為 true，Microsoft Office Communicator 2007 R2。 根據您，如何存取系統，您無法可能最後的主要是未受管理的狀態 （通常是因為群組原則無法套用至您的使用者帳戶）。 相反地，在 Lync Server 和商務用 Skype，則是 nothing 屬於左未受管理。 這是因為任何動作，您就不用全域原則與設定將一律會強制執行。

我們由 「 就不需任何其他項目 」 代表什麼意義？ Skype 商務 Online，若是沒錯，可以建立原則*標記的範圍*，或管理的圓球。 在標記範圍 （也就是*個別使用者範圍*） 中建立的原則優先於全域範圍建立原則。 換句話說，每一使用者原則將會一律優先於全域原則。 例如，您可能有兩個外部使用者存取原則。 全域原則會禁止使用者擁有公用立即訊息 (IM) 提供者，例如 Windows Live 帳戶的人通訊。 個別使用者原則，AllowPublicIMCommunication，可讓與公用 IM 提供者的通訊。

您可能也有兩位使用者： Ken Myer 與 Pilar Ackerman。 Ken Myer 已被指派個別使用者原則。 為 pilar Ackerman 尚未被指派每位使用者的原則;也就是說，她管理由全域外部存取原則。 下表顯示哪些使用者 （如果有的話） 可以與彼此公用 IM 提供者：


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
<td><p>使用者可以與彼此公用 IM 提供者</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>


如您所見，Ken Myer 會允許與公用 IM 提供者進行通訊。 這是因為中指派給他的每一使用者原則的設定會覆寫全域原則設定。 為 pilar Ackerman 無法與公用 IM 提供者進行通訊。 這是因為她會受全域原則，並全域原則禁止這類通訊。

由 Office 365 支援人員，必須為您建立個別使用者原則。 建立原則之後，您可以再指派這些使用者使用適當的**授與 Cs**指令程式 (例如， [Grant-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy))。 每一使用者原則很容易識別因為原則 Identity 一律為開頭標記**前置詞**。 例如：

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> 回到開發早期 Lync Server 2010 的標記<STRONG>前置詞</STRONG>日期。 這些天內個別使用者原則已稱為<EM>標籤原則</EM>，並已識別的標記<STRONG>前置詞</STRONG>。 這些原則現在更精確地稱為<EM>個別使用者原則</EM>，而且標籤範圍更精確地稱為<EM>每個使用者範圍</EM>。 不過，基於技術考量，已永遠不會變更標記<STRONG>前置詞</STRONG>。



</div>

使用 Skype for Business Online 和 Windows PowerShell 時使用的另一個重要字詞是*租用戶*。 當您設定 「 Skype for Business Online 帳戶時，指派新部署的租用戶識別碼號碼，也就是類似這樣的全域唯一識別碼 (GUID):

    bf19b7db-6960-41e5-a139-2aa373474354

Skype 商務 Online 指令程式的幾個要求您輸入的租用戶識別碼，每當您執行 cmdlet。 您必須輸入的租用戶識別碼，即使您已登入，並只能有一個租用戶。 幸好，您不需要記下租用戶識別碼。 您可以隨時擷取租用戶識別碼，藉由執行下列 Windows PowerShell 命令：

    Get-CsTenant | Select-Object TenantId

當然，了解等全域範圍和個別使用者範圍 （或標籤範圍） 之間的差異是只一半。 務必要知道當 （或即使） 您可以使用這些範圍。 相同是身分識別和 tenant 參數，則為 true。 下列主題說明不同的 Skype for Business Online 指令程式如何使用身分識別、 範圍和 tenant 參數：

  - [Skype 商務 Online 中使用全域範圍的指令程式](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [Skype 商務 Online 中使用全域範圍和標籤範圍的指令程式](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [Skype 商務 Online 中使用的使用者身分識別的指令程式](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [Skype 商務 Online 中使用的使用者身分識別和標籤範圍的指令程式](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [Skype 商務 Online 中使用 Tenant 參數的指令程式](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [Skype 商務 Online 中使用的會議提供者身分識別的指令程式](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Skype 商務 Online 中不需要使用某個範圍或身分識別的指令程式](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

