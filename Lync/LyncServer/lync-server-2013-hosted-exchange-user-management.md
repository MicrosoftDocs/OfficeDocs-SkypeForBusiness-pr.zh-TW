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
ms.openlocfilehash: 1cceaeaa869d1e058251a62d237c563143a4ae4c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Lync Server 2013 中的主控 Exchange 使用者管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

若要為 Lync Server 2013 使用者提供語音信箱服務，其信箱位於主控 Exchange 服務上，您必須為主控的語音信箱啟用使用者帳戶。

<div>


> [!NOTE]  
> 在 Lync Server 2013 使用者可以啟用裝載的語音信箱之前，必須先部署適用于對應使用者帳戶的主控語音信箱原則。 原則可以是全域、網站或每位使用者在範圍內，只要它套用至您想要啟用的使用者。 如需詳細資訊，請參閱<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的主控語音信箱原則</A>。



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>msExchUCVoiceMailSettings 屬性

Lync Server 2013 引進新的使用者屬性，名為**msExchUCVoiceMailSettings**，它是 Lync Server 2013 Active Directory 架構準備的一部分所建立。 此多重值屬性可容納 Lync Server 2013 和主控 Exchange 服務共用的語音信箱設定。

在某些情況下，裝載 Exchange 服務可能會在啟用 Exchange UM 的程式中設定 msExchUCVoiceMailSettings 屬性的值，或將信箱轉移至主控 Exchange 伺服器的過程中。 如果 Exchange 未設定此屬性，Lync Server 2013 系統管理員必須執行 Set-CsUser Cmdlet 來設定此屬性，如本主題稍早所述。

下表顯示內容的索引鍵/值對及其作者。

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>MsExchUCVoiceMailSettings 屬性索引鍵/值組

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>值</th>
<th>作者</th>
<th>意義</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchangeHostedVoiceMail = 1</p></td>
<td><p>Exchange</p></td>
<td><p>Exchange Server 已啟用使用者的裝載 UM 存取。 Exchange UM 路由應用程式會檢查使用者的主控語音信箱原則，以取得路由詳細資料。</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>Exchange</p></td>
<td><p>Exchange Server 已停用使用者的裝載 UM 存取。</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>使用者已啟用 Lync Server 2013 的託管 UM 存取。 Lync Server 2013 ExUM 路由應用程式會檢查使用者的主控語音信箱原則，以取得路由詳細資料。</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail = 0</p></td>
<td><p>Lync Server</p></td>
<td><p>Lync Server 2013 已停用使用者的裝載 UM 存取。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 如果此屬性已有一個不同的 Lync Server 2013 機碼/值組值 (CSHostedVoiceMail = 0 或 CSHostedVoiceMail = 1) ，則警告會指出該屬性可能是由其他應用程式所管理。 例如，如果索引鍵/值組 ExchangeHostedVoiceMail = 0 或 ExchangeHostedVoiceMail = 1 已存在，就會顯示警告。 在此情況下，您可以透過編輯 Active Directory 來變更值，或執行下列 Cmdlet，將值設定為 null：<BR>Set-CsUser –身分識別使用者– HostedVoicemail $null



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>為使用者啟用主控語音信箱

若要讓使用者的語音信箱呼叫路由傳送至主控 Exchange UM，您必須執行 Set-CsUser Cmdlet 來設定*HostedVoiceMail*參數的值。 這個參數也會向 Lync Server 2013 發出「呼叫語音信箱」指示器。

  - 下列範例會為主控語音信箱啟用 Pilar Ackerman 的使用者帳戶：
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    此 Cmdlet 會驗證主控的語音信箱原則 (全域、網站層級或每位使用者) 適用于此使用者。 若未套用原則，指令 Cmdlet 會失敗。

  - 下列範例會停用 Pilar Ackerman 的使用者帳戶進行主控語音信箱：
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    此 Cmdlet 會驗證沒有任何主控的語音信箱原則 (全域、網站層級或每位使用者) 適用于此使用者。 若原則已套用，指令 Cmdlet 會失敗。

如需使用 Set-CsUser Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。

</div>

</div>

<span> </span>

</div>

</div>

</div>

