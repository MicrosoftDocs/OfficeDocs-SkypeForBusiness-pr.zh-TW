---
title: Lync Server 2013：主控語音信箱原則
description: Lync Server 2013：主控語音信箱原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57461f4ffd2c6f2cd733dd7ec2c945c9e7b801c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550099"
---
# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Lync Server 2013 中的主控語音信箱原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

「裝載 *語音信箱原則* 」會為 Lync Server 2013 ExUM 路由應用程式提供資訊，告知其信箱位於裝載 Exchange 服務上之使用者的通話位置。

<div>


> [!NOTE]  
> 主控的語音信箱原則只有在 Lync Server 2013 與主控 Exchange UM 的整合時才需要。 與內部部署 Exchange UM 的整合不需要這些功能。



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>主控語音信箱原則範圍

「主控語音信箱原則」範圍決定原則適用的階層層級。 您可以設定具有下列範圍層級的主控語音信箱原則：

  - *全域*原則可能會影響 Lync Server 2013 部署中的所有使用者。 如果使用者已啟用主控 Exchange UM 存取，但尚未被指派個別使用者原則，而且尚未將網站原則指派給使用者的網站，則會套用全域原則。 通用原則是隨 Lync Server 2013 一起安裝。 您可以修改它以符合您的需求，但是您無法重新命名或刪除。

  - *網站*原則可能會影響位於已定義原則之網站上的所有使用者。 若使用者已設定為主控 Exchange UM 存取，但尚未指派個別使用者原則，則會套用網站原則。

  - *每一使用者*原則只會影響個別的使用者或群組。 若要強制執行個別使用者原則，您必須將原則明確指派給個別的使用者、群組和連絡人物件。

<div>


> [!NOTE]  
> 在大多數情況下，只需要一個主控語音信箱原則。 您通常可以修改全域原則，以符合您的所有需求。 如果您部署多個主控的語音信箱原則，則所有此類原則都具有每一使用者範圍。



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>主控語音信箱原則屬性

語音信箱原則定義兩個屬性，Lync Server 2013 ExUM 路由應用程式會在傳送至主控 Exchange UM 實現的 INVITE 郵件要求 URI 中插入：

  - **目的地：** 主控 Exchange UM 服務的完整功能變數名稱 (FQDN) 。 內部部署 Lync Server Edge Server 會使用此值進行路由傳送。
    
    <div>
    

    > [!NOTE]  
    > Exchange Online 的 FQDN 是 exap.um.outlook.com。

    
    </div>

  - **組織：** 主控您的 Lync Server 2013 使用者信箱之主控 Exchange UM 服務上租使用者的 FQDN。 語音信箱原則可以包含多個組織。 若原則中包含多個組織，此屬性必須是以逗號分隔的 Exchange 伺服器租使用者，該清單會家用您的 Lync Server 2013 使用者信箱。

<div>


> [!NOTE]  
> 您裝載的 Exchange UM 服務的租使用者系統管理員會提供必要的目的地和組織屬性設定值。 若要設定原則，您必須執行 New-CsHostedVoicemailPolicy Cmdlet，或使用 Set-CsHostedVoicemailPolicy Cmdlet 來修改存在 (例如，全域原則) 。



</div>

如需管理主控語音信箱原則的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - New-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>Per-User 語音信箱原則指派

如果您裝載的語音信箱原則是以每個使用者範圍定義，您必須明確指派它。 您可以執行 Grant-CsHostedVoicemailPolicy Cmdlet，將原則指派給個別使用者或群組。

如需指派或移除個別使用者的主控語音信箱原則的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

