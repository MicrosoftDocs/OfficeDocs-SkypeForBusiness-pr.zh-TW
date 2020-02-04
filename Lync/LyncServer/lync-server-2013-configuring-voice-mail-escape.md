---
title: Lync Server 2013：設定語音信箱轉義
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c32d3bbc39d8f18e30153193c1e722db1ec9d50e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>在 Lync Server 2013 中設定語音信箱轉義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

當使用者設定同時撥打至行動電話時，如果行動電話關閉、不使用電池電源或超出範圍，通常會將呼叫者路由到使用者的個人語音信箱。 使用 Lync Server 2013，使用者可以選擇要將商務相關通話路由至其公司語音信箱系統。 具體來說，您可以設定計時器，並在已定義的時間範圍內，由承運人的語音信箱來應答通話，Lync Server 會中斷與載波語音信箱系統（與使用者的個人語音信箱）的連線，而使用者的剩餘公司系統中的端點持續撥打。 如此一來，來電者就會自動路由到使用者的公司語音信箱。

此設定是在語音原則層級使用 Lync Server Management Shell Cmdlet （ **CsVoicePolicy**）執行，並使用下列參數。

<div>

## <a name="to-configure-voice-mail-escape"></a>若要設定語音信箱轉義

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  指定下列參數來**設定-CsVoicePolicy**：
    
      - **EnableVoicemailEscapeTimer** -啟用或停用轉義計時器。
    
      - **PSTNVoicemailEscapeTimer** -指定超時值（以毫秒為單位）。 預設值為1500毫秒，值的範圍可以是0毫秒到8000毫秒。

</div>

<div>

## <a name="example"></a>範例

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定用於授權撥號功能和權限的語音原則和 PSTN 使用方式記錄](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

