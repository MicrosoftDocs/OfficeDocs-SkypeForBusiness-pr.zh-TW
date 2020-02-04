---
title: Lync Server 2013：主控 Exchange 使用者管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23289399e4eee4a654b41f2978191a6329739b4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Lync Server 2013 中的主控 Exchange 使用者管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

若要為 Lync Server 2013 使用者提供語音信箱服務，而其信箱是位於託管 Exchange 服務的使用者，您必須啟用其使用者帳戶來存放託管的語音信箱。

<div>


> [!NOTE]  
> 在 Lync Server 2013 使用者可以啟用託管語音信箱之前，必須先部署適用于對應使用者帳戶的託管語音信箱原則。 只要將原則套用到您想要啟用的使用者，原則就可以是全域、網站或每位使用者。 如需詳細資訊，請參閱<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中託管的語音信箱原則</A>。



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>MsExchUCVoiceMailSettings 屬性

Lync Server 2013 引入一個名為**msExchUCVoiceMailSettings**的新使用者屬性，該使用者是作為 Lync Server 2013 Active Directory 架構準備的一部分建立的。 這個多重值屬性可保留 Lync Server 2013 和託管 Exchange 服務所共用的語音信箱設定。

在某些情況下，託管 Exchange 服務可能會在啟用 Exchange UM 的程式中設定 msExchUCVoiceMailSettings 屬性的值，或在將信箱轉移至託管 Exchange 伺服器的程式期間設定。 如果 Exchange 未設定此屬性，則 Lync Server 2013 系統管理員必須執行 Move-csuser Cmdlet 來設定它，如本主題前面所述。

屬性的鍵/值對及其作者如下表所示。

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>MsExchUCVoiceMailSettings 屬性鍵/值對

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>值</th>
<th>撰寫</th>
<th>意味</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchangeHostedVoiceMail = 1</p></td>
<td><p>證券</p></td>
<td><p>使用者已啟用 Exchange Server 的託管 UM 存取權。 Exchange UM 路由應用程式將會檢查使用者的託管語音信箱原則，以取得路由詳細資料。</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>證券</p></td>
<td><p>已停用 Exchange Server 的託管 UM 存取的使用者。</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>使用者已啟用 Lync Server 2013 的託管 UM 存取權。 Lync Server 2013 ExUM 路由應用程式將會檢查使用者的託管語音信箱原則，以取得路由詳細資料。</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail = 0</p></td>
<td><p>Lync Server</p></td>
<td><p>已停用 Lync Server 2013 的託管 UM 存取的使用者。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 如果屬性已有一個 Lync Server 2013 鍵/值對以外的值（CSHostedVoiceMail = 0 或 CSHostedVoiceMail = 1），則會出現警告，指出該屬性可能是由不同的應用程式來管理。 例如，如果鍵/值對 ExchangeHostedVoiceMail = 0 或 ExchangeHostedVoiceMail = 1 已存在，則會顯示警告。 在這種情況下，您可以透過編輯 Active Directory 來變更值，或執行下列 Cmdlet，將此值設定為 null：<BR>Move-csuser –身分識別使用者– HostedVoicemail $null



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>允許使用者擁有託管的語音信箱

若要讓使用者的語音信箱呼叫路由至託管 Exchange UM，您必須執行 Move-csuser Cmdlet 來設定*HostedVoiceMail*參數的值。 這個參數也會通知 Lync Server 2013，以淺您的「撥號語音信箱」指標。

  - 下列範例會針對託管語音信箱啟用 Pilar 方的使用者帳戶：
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    此 Cmdlet 會驗證託管的語音信箱原則（全域、網站層級或每位使用者）適用于此使用者。 如果沒有套用任何原則，則 Cmdlet 失敗。

  - 下列範例會針對託管語音信箱停用 Pilar 方的使用者帳戶：
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    此 Cmdlet 會確認沒有任何託管的語音信箱原則（全域、網站層級或每位使用者）適用于此使用者。 如果已套用原則，則 Cmdlet 會失敗。

如需有關使用 Move-csuser Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。

</div>

</div>

<span> </span>

</div>

</div>

</div>

