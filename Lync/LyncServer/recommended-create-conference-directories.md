---
title: (建議) 建立會議目錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e912beac1eeffe3214f8a8d638926d84f547a270
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a>(建議) 建立會議目錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-10-03_

在使用 Lync 2013 時，會議目錄會維持參與者用來加入會議的字母數位會議 ID 之間的對應，以及電話撥入式會議參與者用來加入會議的僅限數位會議 ID。 會議 ID 的格式如下所示：

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

建立多個會議目錄可確保會議 Id 保持不變，直到建立大量的會議為止。 在每位使用者有典型會議數的組織中，我們建議您為池中的每個999使用者建立一個會議目錄。 使用這種準則，會議 Id 通常可以保持很小的狀態。 不過，一旦會議目錄數量（跨多個池）超過9個，會議 ID 長度就會增長以支援其他會議。

<div>

## <a name="creating-a-conference-directory"></a>建立會議目錄

1.  在 Lync Server 管理命令介面中，輸入下列 Cmdlet：
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    例如，下列程式會建立一個在 pool atl-cs-001.litwareinc.com 上託管的身分識別42的會議目錄：
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的電話撥入式會議需求](lync-server-2013-dial-in-conferencing-requirements.md)  


[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

