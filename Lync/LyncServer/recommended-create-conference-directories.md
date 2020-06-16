---
title: 推薦建立會議目錄
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5ce338c6eb67f545439bfe1e9f2134cd7f1e6d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a>推薦建立會議目錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-10-03_

會議目錄會維護在使用 Lync 2013 時，參與者用來加入會議的字母數位會議 ID 之間的對應，以及電話撥入式會議參與者用來加入會議的僅限數位會議識別碼。 會議識別碼的格式如下：

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

建立多個會議目錄可確保會議 IDs 持續縮短，直到建立大量會議為止。 在組織中，每位使用者的會議數目為典型，我們建議您針對集區中的每個999使用者建立一個會議目錄。 使用此指導方針時，會議 IDs 通常可以保持很小。 不過，當會議目錄的數目（跨集區）超過9時，會議識別碼長度會成長以支援其他會議。

<div>

## <a name="creating-a-conference-directory"></a>建立會議目錄

1.  在 Lync Server 管理命令介面中，輸入下列 Cmdlet：
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    例如，下列所建立的會議目錄使用 identity 42，主控于集區 atl-cs-001.litwareinc.com：
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的電話撥入式會議需求](lync-server-2013-dial-in-conferencing-requirements.md)  


[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

