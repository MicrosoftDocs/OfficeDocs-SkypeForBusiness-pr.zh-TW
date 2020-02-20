---
title: 了解常設聊天室成員資格
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
ms.openlocfilehash: 6f2422e1b7191680b6ff81ecec7fb60d82a9ef10
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a>了解常設聊天室成員資格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-22_

使用者的存取權的常設聊天室管理成員資格;使用者必須能夠傳送及讀取郵件聊天室的成員。 只有**簡報者**具有聊天室與指定的 affiliation 允許使用**張貼至視聽中心聊天室**。 視聽中心是一種聊天室 （另一個是**標準模式**），其中只有簡報者可以張貼及每個人都可以讀取。

此外，常設聊天室操作類別的規則] 下。 如需類別的詳細資訊，請參閱[管理類別、 聊天室及 Lync Server 2013 中增益集](lync-server-2013-managing-categories-rooms-and-add-ins.md)，以及在本主題稍後的區段 」 類別範圍設定的運作方式 」 和 「 聊天室類別策略 」。

常設聊天室管理員可以建立及管理聊天室類別。 建立及管理聊天室類別的一部分，常設聊天室系統管理員可以設定已設為 [成員] 或 [建立者的特定類別的聊天室存取的主體 （Active Directory 網域服務群組、 容器，以及使用者）。

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Active Directory 網域服務和常設聊天室

Persistent Chat Server 會依賴的常設聊天室的內部使用者的集區的 Active Directory。 安裝常設聊天室 （用戶端） 之後，您可以將使用者和使用者群組的網域新增至聊天室類別。 然後可以將這些使用者和群組新增至聊天室類別的成員資格。

<div>


> [!IMPORTANT]  
> 您必須確定有想要對其常設 Chat room(s) 進行變更的使用者沒有重複的名稱。 如果存在重複的使用者名稱，請將它們變更為不同的名稱，以解除封鎖來自進行這些變更的使用者。 如果使用者在 Active Directory 中有重複的名稱，並嘗試在其 room(s) 中進行變更，會出現錯誤訊息，提示使用者連絡系統管理員以解決方法。



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>類別範圍的運作方式

類別指定的所有使用者和群組可在該類別中，根據其**AllowedMembers**屬性常設聊天室聊天室成員資格清單中的成員。 例如，如果您將類別的**AllowedMembers**為 contoso.com，您可以新增任何群組或使用者在*contoso 公司*的成員身分至該類別中聊天室。 如果您設定類別以*銷售* **AllowedMembers** ，只有群組及此通訊群組清單中的使用者可以新增為成員至該類別中聊天室。 同樣地， **Creators**屬性可讓您控制可以建立該類別中聊天室。 聊天室建立之後，從**AllowedMembers**群組的任何人都可以指定做為**管理員**的聊天室 （例如，成員資格變更及核准） 上的進行中的管理作業。

類別定義**AllowedMembers**和**Creators**有下列優點：

  - 此類別中的所有聊天室都 eng 類別層級設定的限制。 您可以使用這個單獨分開的聊天室根據業務需要和存取原則。

  - 在 [**建立者**] 清單中的使用者可以建立新聊天室該類別中。 如果您想要實作有限的數目的組織中的人員可以在其中建立聊天室的系統，此控制項可以用來符合此需求。

</div>

<div>

## <a name="room-category-strategies"></a>聊天室類別策略

類別**AllowedMembers**必須包含將使用此類別中的任何常設聊天室會議室的所有使用者。 根據您的需求來保護商務資料，並確保適當的存取層級，您可能想要定義一個或多個類別，來指定誰可以搜尋並參與聊天室。 如果您想要允許只有一組特定使用者 （中央技術服務人員或只開放全職員工） 來建立會議室，您可以範圍以滿足此需求類別**建立者**。

類別也可以用來建立道德管束。 道德管束防止在組織中任何衝突的利息。 例如，系統管理員可以建立聊天室類別中的 traders 只而另一個類別中聊天室可以用來分析師僅。

<div>


> [!NOTE]  
> 在 Lync Server 2013，Persistent Chat Server，我們不支援同盟使用者存取。 如果有從舊版 Persistent Chat Server 中的同盟使用者的聊天室，他們將會移轉。 同盟的使用者新增為已停用的主體。



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>範圍縮小至使用者群組的成員

當您新增網域至類別時，其群組物件都包含在該網域的使用者群組可用於您，讓您可以將它們指定為該類別中聊天室的成員。

我們建議，作為一般規則，您使用 Active Directory 容器、 網域及組織單位，例如定義類別**AllowedMembers**和**Creators**。 您可以將物件從任何網域新增至**AllowedMembers**或**建立者**的清單。 只有**AllowedMembers**或**建立者**清單中的物件可以新增至該類別底下的聊天室。

</div>

</div>

<span> </span>

</div>

</div>

</div>

