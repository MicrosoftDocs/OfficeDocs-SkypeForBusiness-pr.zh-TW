---
title: 瞭解常設聊天室成員資格
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b4eb5fbe4342c1bd6bcb3bbb842e076e5863ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a>瞭解常設聊天室成員資格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

使用者存取持久聊天室是由成員資格所管理;使用者必須是聊天室的成員，才能張貼及閱讀郵件。 只有已指定隸屬于聊天室的**簡報者**，才可以使用**張貼功能來 Auditorium 會議室**。 Auditorium 是一種聊天室（另一個是**標準**），只有簡報者可以張貼，而且所有人都可以閱讀。

此外，持續聊天室也會在類別的規則下運作。 如需類別的詳細資訊，請參閱在[Lync Server 2013 中管理類別、會議室和增益集](lync-server-2013-managing-categories-rooms-and-add-ins.md)，以及本主題後面的「類別作用中的運作方式」和「會議室類別戰略」章節。

持續聊天系統管理員可以建立及管理聊天室類別。 在建立及管理聊天室類別的過程中，持續性聊天管理員可以設定主體（Active Directory 網域服務群組、容器和使用者），這些使用者有權存取屬於特定類別之聊天室的成員或會議室。

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Active Directory 網域服務和持續聊天

持續聊天伺服器會依賴內部持久聊天使用者池的 Active Directory。 安裝持續聊天（用戶端）之後，您可以將使用者和使用者群組的網域新增至聊天室類別。 然後，您可以將這些使用者和群組新增至聊天室類別的成員資格。

<div>


> [!IMPORTANT]  
> 您必須確定要對其持續聊天室進行變更的使用者，不存在重複的名稱。 如果有重複的使用者名稱存在，請將其變更為不同的名稱，以解除封鎖使用者進行這些變更。 如果使用者在 Active Directory 中有重複的名稱，並嘗試在聊天室中進行變更，則會出現錯誤訊息，提示使用者與管理員聯繫以進行解決。



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>類別作用中的運作方式

類別會根據其**AllowedMembers**屬性，指定可成為該類別之持續聊天室的成員資格清單中的所有使用者和群組。 例如，如果您將類別的**AllowedMembers**設定為 contoso.com，您可以在*contoso*中新增任何群組或使用者作為該類別中的聊天室。 如果您將類別的**AllowedMembers**設定為 [*銷售*]，則只有此通訊群組清單中的群組和使用者可以新增為該類別中的聊天聊天室成員。 同樣地，[**創意者**] 屬性可讓您控制誰可以在該類別中建立聊天室。 在您建立聊天室之後，您可以將來自**AllowedMembers**群組的任何人指派為系統**管理員**，以便在會議室上進行持續的管理作業（例如，成員資格變更與核准）。

定義類別的**AllowedMembers**和**創意者**具有下列優點：

  - 此類別中的所有聊天室都是由在類別層級設定的限制來系結。 您可以根據業務需求與存取原則，使用這個功能來隔離聊天室。

  - [**製作者**清單] 中的使用者可以在該類別中建立新的聊天室。 如果您想要實現組織中受限制的人員可以建立聊天室的系統，此控制項可以用來符合該需求。

</div>

<div>

## <a name="room-category-strategies"></a>會議室類別策略

類別的**AllowedMembers**必須包含所有將在此類別中使用任何持續聊天室的使用者。 根據您保護商務資料的需求，並確保適當的存取層級，您可能會想要定義一或多個類別，以指定誰可以搜尋及參與會議室。 如果您想要只允許一組特定的使用者（中央支援人員或只有全職員工）來建立會議室，您可以將類別的建立**者**限定為符合該需求。

您也可以使用類別來建立道德的牆。 道德的背景牆可避免組織中任何利益衝突的情況。 例如，管理員只能在商貿類別中建立聊天室，而其他類別的聊天室只能由分析師使用。

<div>


> [!NOTE]  
> 在 Lync Server 2013 的持續聊天伺服器中，我們不支援聯盟使用者的存取權。 如果在舊版本的持久性聊天伺服器中有來自同盟使用者的聊天，他們將會被遷移。 聯盟使用者會新增為停用的主體。



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>將成員收縮到使用者群組

當您將網域新增至某個類別時，您可以使用該網域中包含其群組物件的使用者群組，以便將其指定為該類別中的會議室成員。

我們建議您使用 Active Directory 容器（例如網域和組織單位）來定義類別的**AllowedMembers**及建立**者**，以作為一般規則。 您可以將任何網域中的物件新增至**AllowedMembers**或**創意者**清單。 只有**AllowedMembers**或**創意者**清單中的物件可以新增到該類別下的聊天室中。

</div>

</div>

<span> </span>

</div>

</div>

</div>

