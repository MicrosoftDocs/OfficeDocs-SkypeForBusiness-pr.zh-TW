---
title: Lync Server 2013： 設定語音信箱逸出
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
ms.openlocfilehash: 131b36b87a3d930662cdd863dd4ebc1d0d69163e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>在 Lync Server 2013 中設定語音信箱逸出

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-22_

當使用者設定行動電話同時響鈴時，來電者將通常會路由傳送至使用者的個人語音信箱如果行動電話已關機、 電池電力耗盡或超出範圍。 與 Lync Server 2013 中，使用者可以選擇將業務相關的通話路由傳送至其公司的語音信箱系統。 具體而言，可以設定計時器，而且如果所定義的時間範圍內的電信業者的語音信箱接聽電話，Lync Server 會從電信業者的語音郵件系統 （和使用者的個人語音信箱），中斷時剩餘的使用者端點公司系統中的繼續執行響鈴。 如此一來，來電者會自動路由傳送至使用者的企業語音信箱。

此設定是在語音原則層級，使用下列參數使用 Lync Server 管理命令介面 cmdlet **Set-csvoicepolicy**，在執行。

<div>

## <a name="to-configure-voice-mail-escape"></a>若要設定語音信箱逸出

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  指定要**Set-csvoicepolicy**的下列參數：
    
      - **EnableVoicemailEscapeTimer** -啟用或停用逸出計時器。
    
      - **PSTNVoicemailEscapeTimer** -以毫秒為單位指定的逾時值。 預設值為 1500年毫秒，且值可介於 0 毫秒到 8000 （毫秒）。

</div>

<div>

## <a name="example"></a>範例

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a>請參閱


[設定語音原則和 PSTN 使用方式記錄，以授權撥號功能及 Lync Server 2013 中的權限](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

