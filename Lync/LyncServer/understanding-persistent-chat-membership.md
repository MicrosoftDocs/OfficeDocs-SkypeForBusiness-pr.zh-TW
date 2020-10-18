---
title: 瞭解 Persistent Chat 成員資格
description: 瞭解 Persistent Chat 成員資格。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63e0d26ea56552d8906ab9a5cf216a7026868017
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579599"
---
# <a name="understanding-persistent-chat-membership"></a>瞭解 Persistent Chat 成員資格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

使用者存取持久聊天室是由成員資格管理;使用者必須是聊天室的成員，才能張貼和閱讀郵件。 只有具有聊天室關聯的 **簡報者** ，才可以使用 **張貼功能來視聽中心會議室**。 視聽中心是一種類型的聊天室 (另一種是 **普通**) ，其中只有簡報者可以張貼，而且所有人都可以讀取。

此外，Persistent 聊天室會在類別的規則下運作。 如需類別的詳細資訊，請參閱 [管理 Lync Server 2013 中的類別、聊天室及增益集](lync-server-2013-managing-categories-rooms-and-add-ins.md)，以及本主題稍後的「類別範圍的運作方式」和「會議室類別策略」一節。

Persistent Chat 系統管理員可以建立及管理聊天室類別。 在建立及管理聊天室類別的過程中，Persistent Chat 管理員可以將主體設定 (Active Directory 網域服務群組、容器和使用者) ，該使用者有權存取屬於特定類別之聊天室的成員或建立者。

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Active Directory 網域服務和持續聊天

Persistent Chat Server 依賴內部 Persistent Chat 使用者之集區的 Active Directory。 在您安裝 Persistent Chat (用戶端) 之後，您可以將使用者和使用者群組的網域新增至聊天室類別。 然後，您可以將這些使用者和群組新增至您的聊天室類別的成員資格。

<div>


> [!IMPORTANT]  
> 您必須確定要對其持久聊天室 () 的使用者進行變更時，是否沒有重複的名稱。 如果存在重複的使用者名稱，請將其變更為不同的名稱，以解除封鎖使用者進行這些變更。 如果使用者在 Active Directory 中有重名的名稱，並嘗試在其聊天室中進行變更 (s) 時，會出現錯誤訊息，提示使用者與系統管理員聯繫以進行解析。



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>類別範圍的運作方式

類別會根據其 **AllowedMembers** 屬性，指定其成員資格清單中的成員在該類別中的成員資格清單中的所有使用者和群組。 例如，如果您將類別的 **AllowedMembers** 設定為 contoso.com，您可以將 *contoso* 中的任何群組或使用者新增至該類別中的聊天室的成員。 如果您將類別上的 **AllowedMembers** 設定為 *Sales*，則只有此通訊群組清單中的群組和使用者可以新增為該類別中聊天室的成員。 同樣地，建立 **者** 屬性可讓您控制哪些人員可以在該類別建立聊天室。 在建立聊天室之後，可以將 **AllowedMembers** 群組中的任何人指派為該會議室上的日常管理作業的 **管理員** (例如，成員資格變更和核准) 。

定義類別的 **AllowedMembers** 和建立 **者** 具有下列優點：

  - 此類別中的所有聊天室都受限於在類別層級設定的限制。 您可以使用此功能，根據業務需求和存取原則隔離聊天室。

  - 建立 **者** 清單中的使用者可以在該類別中建立新聊天室。 如果您想要執行的系統中組織中的人員人數有限，可以建立聊天室，此控制項可用於符合該需求。

</div>

<div>

## <a name="room-category-strategies"></a>會議室類別策略

類別的 **AllowedMembers** 必須包括將在此類別中使用任何持續聊天室的所有使用者。 根據您保護商務資料的需求，並確定適當的存取層級，您可能想要定義一或多個類別，以指定誰可以搜尋及參與聊天室。 如果您只想要允許中央技術支援人員 (一組特定的使用者，或是只) 建立會議室的全職員工，您可以限定類別建立 **者** 以滿足此需求。

類別也可以用來建立道德的背景牆。 道德的牆可防止組織利益衝突。 例如，系統管理員可以只為商貿建立一個類別的聊天室，而另一個類別的聊天室只可供分析員使用。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，Persistent Chat Server，我們不支援同盟使用者的存取。 如果舊版 Persistent Chat Server 中的同盟使用者已有聊天版本，將會進行遷移。 同盟使用者已新增為已停用的主體。



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>將成員縮小為使用者群組

當您將網域新增至類別時，您可以使用其 group 物件包含在該網域中的使用者群組，讓您將其指定為該類別中聊天室的成員。

我們建議您使用 Active Directory 容器（如網域和組織單位）來定義類別的 **AllowedMembers** 和建立 **者**，以成為一般規則。 您可以將任何網域中的物件新增至 **AllowedMembers** 或建立 **者** 清單。 只有 **AllowedMembers** 或建立 **者** 清單中的物件可以新增至該類別底下的聊天室。

</div>

</div>

<span> </span>

</div>

</div>

</div>

