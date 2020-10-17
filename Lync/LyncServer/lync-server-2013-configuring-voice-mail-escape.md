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
ms.openlocfilehash: 7c3faf28bdd85f32de1560d35aaf35392fef9746
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516950"
---
# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>在 Lync Server 2013 中設定語音信箱轉義

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

當使用者設定同時響鈴的行動電話時，如果行動電話關閉、電池計量不足或超出範圍，則通常會將來電者路由傳送至使用者的個人語音信箱。 使用 Lync Server 2013，使用者可以選擇要將與業務相關的電話路由傳送至公司語音信箱系統。 具體而言，您可以設定 timer，如果在所定義的時間範圍內，來電者的語音信箱接聽來電，Lync Server 會中斷與電信公司的語音信箱系統的連線 (和使用者的個人語音信箱) ，而使用者在公司系統中的剩餘端點會繼續振鈴。 如此一來，來電者就會自動路由傳送至使用者的公司語音信箱。

使用下列參數，在語音原則層級上使用 Lync Server 管理命令介面 Cmdlet， **Set-CsVoicePolicy**執行此設定。

<div>

## <a name="to-configure-voice-mail-escape"></a>設定語音信箱轉義

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  指定下列要 **Set-CsVoicePolicy**的參數：
    
      - **EnableVoicemailEscapeTimer** -啟用或停用轉義計時器。
    
      - **PSTNVoicemailEscapeTimer** -指定超時值，以毫秒為單位。 預設值為1500毫秒，值的範圍為0毫秒到8000毫秒。

</div>

<div>

## <a name="example"></a>範例

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定語音原則和 PSTN 使用方式記錄，以授權呼叫功能和許可權](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

