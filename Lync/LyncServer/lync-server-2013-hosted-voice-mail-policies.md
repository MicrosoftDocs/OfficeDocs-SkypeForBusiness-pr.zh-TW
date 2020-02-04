---
title: Lync Server 2013：主控語音信箱原則
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
ms.openlocfilehash: 811f975868dad7bc0fcf6d5a2867ca2f3b81cd59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Lync Server 2013 中的主控語音信箱原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

已*託管的語音信箱原則*會提供資訊給 Lync Server 2013 ExUM 路由應用程式，讓您在何處路由其信箱位於託管 Exchange 服務的使用者。

<div>


> [!NOTE]  
> 只有在與託管 Exchange UM 整合 Lync Server 2013 時，才需要託管語音信箱原則。 它們不是與內部部署 Exchange UM 的整合所需要的。



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>已託管的語音信箱原則範圍

已託管的語音信箱原則範圍會決定原則的層次結構層級。 您可以將託管的語音信箱原則設定為下列範圍層級：

  - *全域*原則可能會影響 Lync Server 2013 部署中的所有使用者。 如果使用者已啟用託管 Exchange UM 存取，而且尚未獲指派每個使用者的原則，且尚未將網站原則指派給使用者的網站，則會套用全域原則。 使用 Lync Server 2013 安裝全域原則。 您可以對其進行修改以符合您的需求，但無法重新命名或刪除該檔案。

  - *網站*原則可能會影響託管在已定義策略之網站上的所有使用者。 如果使用者是針對託管 Exchange UM 存取進行設定，且尚未獲指派每個使用者的原則，則會套用網站原則。

  - *每個使用者*的原則只會影響個別的使用者或群組。 若要強制執行每個使用者的原則，您必須將原則明確指派給個別的使用者、群組和連絡人物件。

<div>


> [!NOTE]  
> 在大多數情況下，只需要一個寄宿的語音信箱原則。 您通常可以修改全域原則，以符合您的需求。 如果您部署多個託管的語音信箱原則，所有這類原則都會有每個使用者的範圍。



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>託管的語音信箱原則屬性

語音信箱原則定義了兩個屬性，Lync Server 2013 ExUM 路由應用程式會在傳送到託管 Exchange UM 實現的邀請郵件的要求 URI 中插入：

  - **目的地：** 託管 Exchange UM 服務的完整功能變數名稱（FQDN）。 此值是由內部部署的 Lync Server Edge 伺服器用來進行路由的目的。
    
    <div>
    

    > [!NOTE]  
    > Exchange Online 的 FQDN 是 exap.um.outlook.com。

    
    </div>

  - **組織：** 寄存您的 Lync Server 2013 使用者信箱的託管 Exchange UM 服務上的租使用者 FQDN。 語音信箱原則可以包含多個組織。 如果原則中包含多個組織，此屬性必須是家用 Lync Server 2013 使用者信箱之 Exchange 伺服器租使用者的逗號分隔清單。

<div>


> [!NOTE]  
> 您託管 Exchange UM 服務的租使用者系統管理員會針對您的目的地和組織屬性設定提供必要的值。 若要設定您的原則，您必須執行新的 CsHostedVoicemailPolicy Cmdlet，或使用 CsHostedVoicemailPolicy Cmdlet 來修改現有的（例如，全域原則）。



</div>

如需管理託管語音信箱原則的詳細資訊，請參閱下列 Cmdlet 的 Lync Server 管理命令介面檔：

  - 新-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - CsHostedVoicemailPolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>每個使用者的語音信箱原則指派

如果您託管的語音信箱原則是由每個使用者的範圍所定義，則您必須明確指派它。 您可以執行授與 CsHostedVoicemailPolicy Cmdlet，將原則指派給個別的使用者或群組。

如需指派或移除依使用者裝載的語音信箱原則的詳細資料，請參閱下列 Cmdlet 的 Lync Server 管理命令介面檔：

  - 授與 CsHostedVoicemailPolicy

  - 移除-CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

