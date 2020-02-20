---
title: Lync Server 2013： 主控的語音信箱原則
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
ms.openlocfilehash: 16570331d0d7e154388c51ecb11be591bf3bbd05
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Lync Server 2013 中的主控的語音信箱原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-01_

*裝載語音信箱原則*提供資訊給 Lync Server 2013 ExUM Routing 應用程式的使用者信箱位於裝載 Exchange 服務的電話路由至何處。

<div>


> [!NOTE]  
> 主控的語音信箱原則所需僅適用於 Lync Server 2013 整合與裝載 Exchange UM。 不需要進行與內部部署 Exchange UM 整合。



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>裝載的語音信箱原則範圍

裝載的語音信箱原則範圍會決定在套用原則的階層式層級。 您可以使用下列範圍層級設定主控的語音信箱原則：

  - *全域*原則可能會影響在 Lync Server 2013 部署中的所有使用者。 如果使用者的裝載 Exchange UM 存取已啟用，且未被指派個別使用者原則，且網站原則不已指派給使用者的網站，適用於全域原則。 使用 Lync Server 2013 安裝的全域原則。 您可加以修改以符合您的需求，但您無法重新命名或刪除它。

  - *網站*原則可能會影響所有使用者都位於其定義原則的網站。 如果使用者的裝載 Exchange UM 存取設定，且未被指派個別使用者原則，適用於站台原則。

  - *每位使用者*的原則可能會影響僅限個別使用者或群組。 強制執行的每一使用者原則，您必須明確地將原則指派給個別使用者、 群組和連絡人物件。

<div>


> [!NOTE]  
> 在大多數情況下，只有一個裝載的語音信箱原則是必要的。 您通常可以修改全域原則以符合您的需求。 如果您部署多個託管的語音信箱原則時，所有這類原則有每個使用者範圍。



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>裝載的語音信箱原則屬性

「 語音信箱原則會定義 Lync Server 2013 ExUM Routing 應用程式插入要求 URI，傳送至裝載的 Exchange UM 實作此 INVITE 訊息中的兩個屬性：

  - **目的地：** 主控 Exchange UM 服務的完整的網域名稱 (FQDN)。 這個值是由內部部署 Lync Server Edge Server 用於路由用途。
    
    <div>
    

    > [!NOTE]  
    > Exchange Online 的 FQDN 是 exap.um.outlook.com。

    
    </div>

  - **組織：** 在主控 Exchange UM 服務所在 Lync Server 2013 使用者信箱上的租用戶 FQDN。 「 語音信箱原則可以包含多個組織。 如果在原則中包含了一個以上的組織，這個屬性必須以逗號分隔清單中的 Exchange 伺服器 tenant 該首頁 Lync Server 2013 使用者信箱。

<div>


> [!NOTE]  
> 您的託管式 Exchange UM 服務租用戶系統管理員會提供您的目的地和組織屬性設定必要的值。 若要設定您的原則，您必須執行新增 CsHostedVoicemailPolicy 指令程式，或使用 Set-cshostedvoicemailpolicy cmdlet 來修改其中存在 （例如，全域原則）。



</div>

如需管理裝載的語音信箱原則的詳細資訊，請參閱 Lync Server 管理命令介面文件的下列 cmdlet:

  - 新 CsHostedVoicemailPolicy

  - Set-cshostedvoicemailpolicy

  - Get-cshostedvoicemailpolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>每位使用者的語音信箱原則指派

如果您的裝載的語音信箱原則定義每個使用者範圍，您必須明確地將授權指派。 您可以執行授與 CsHostedVoicemailPolicy 指令程式將原則指派給個別使用者或群組。

如需指派或移除個別使用者裝載語音信箱原則的詳細資訊，請參閱 Lync Server 管理命令介面文件的下列 cmdlet:

  - 授與 CsHostedVoicemailPolicy

  - 移除 CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

