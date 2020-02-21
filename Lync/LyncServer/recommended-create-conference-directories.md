---
title: （建議使用）建立會議目錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37cc13b18ccc936924efffe689ae1975149ffdb3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a>（建議使用）建立會議目錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-10-03_

會議目錄維護參與者使用時使用 Lync 2013 加入會議的英數字元的會議 ID 與電話撥入式會議參與者加入會議所使用的僅限數字鍵台的會議 ID 之間的對應。 會議 ID 的格式如下：

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

建立多個會議目錄，可確保在建立大量的會議之前會議 Id 會保持簡短。 在一般每位使用者的會議數目與組織中，我們建議您在集區中建立一個的每個 999 使用者的會議目錄。 使用此指導方針會議識別碼可以通常是保持小型。 不過，一旦 （整個集區） 的會議目錄的數目超過 9，會議 ID 長度會成長到支援其他會議。

<div>

## <a name="creating-a-conference-directory"></a>建立會議目錄

1.  在 [Lync Server 管理命令介面，輸入下列 cmdlet:
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    例如，下列範例會建立裝載在 atl-cs-001.litwareinc.com 集區身分識別 42，會議目錄-atl-cs-001.litwareinc.com:
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的電話撥入式會議需求](lync-server-2013-dial-in-conferencing-requirements.md)  


[新 CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

