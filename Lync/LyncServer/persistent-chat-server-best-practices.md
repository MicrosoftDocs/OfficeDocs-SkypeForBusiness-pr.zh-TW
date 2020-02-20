---
title: 常設聊天室伺服器最佳作法
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61b183e442312647222f92a26effd064b2109434
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="4dd3e-102">常設聊天室伺服器最佳作法</span><span class="sxs-lookup"><span data-stu-id="4dd3e-102">Persistent Chat Server best practices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dd3e-103">_**主題上次修改日期：** 2012年-10-06_</span><span class="sxs-lookup"><span data-stu-id="4dd3e-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="4dd3e-104">當您建立類別和常設聊天室並且設計範圍與成員資格時，下列秘訣可協助您規劃：</span><span class="sxs-lookup"><span data-stu-id="4dd3e-104">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="4dd3e-105">如果貴公司不需要道德管束，不會逐漸類別樹狀目錄中的範圍。</span><span class="sxs-lookup"><span data-stu-id="4dd3e-105">If your company does not require an ethical wall, do not narrow the scope in your category tree.</span></span> <span data-ttu-id="4dd3e-106">置於一個類別的範圍中的所有使用者，並建立該類別中的所有聊天室。</span><span class="sxs-lookup"><span data-stu-id="4dd3e-106">Put all your users in the scope of one category, and create all chat rooms in that category.</span></span> <span data-ttu-id="4dd3e-107">接下來，使用僅限成員資格清單來授與或限制每個聊天室的存取。</span><span class="sxs-lookup"><span data-stu-id="4dd3e-107">Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="4dd3e-108">在大多數情況下，您應讓使用者能夠建立新聊天室，以便關於新主題的討論區可以啟動隨時。</span><span class="sxs-lookup"><span data-stu-id="4dd3e-108">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time.</span></span> <span data-ttu-id="4dd3e-109">執行此動作，以列出**AllowedMembers**清單相同的**建立者**。</span><span class="sxs-lookup"><span data-stu-id="4dd3e-109">Do this by making the **Creators** list the same as the **AllowedMembers** list.</span></span> <span data-ttu-id="4dd3e-110">不過，如果您想要允許只有中央支援小組或指定要建立之聊天室的使用者，然後進行**Creators**清單為適當的子集。</span><span class="sxs-lookup"><span data-stu-id="4dd3e-110">However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="4dd3e-111">授與每個聊天室的完整名稱和說明，摘要說明其中它的方式符合您的組織。</span><span class="sxs-lookup"><span data-stu-id="4dd3e-111">Give each chat room a complete name and description summary that describes where it fits in with your organization.</span></span> <span data-ttu-id="4dd3e-112">因為使用者無法查看的類別名稱，在使用聊天室時，您無法仰賴以協助使用者決定預定的討論論壇聊天室的類別名稱。</span><span class="sxs-lookup"><span data-stu-id="4dd3e-112">Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="4dd3e-113">您可能想要有自訂聊天室建立工作流程，如果您有特定的命名慣例或其他的存取控制或實作驗證。</span><span class="sxs-lookup"><span data-stu-id="4dd3e-113">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="4dd3e-114">常設聊天室組態可讓您自訂**RoomManagementUrl**成您主控。</span><span class="sxs-lookup"><span data-stu-id="4dd3e-114">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="4dd3e-115">例如，當使用者按一下其 Lync 用戶端中**建立會議室**，他們可以重新導向至您的自訂解決方案。</span><span class="sxs-lookup"><span data-stu-id="4dd3e-115">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="4dd3e-116">建立各種不同的增益集，以將文字方塊帶到聊天室其他商務資料中增強的聊天室的經驗。</span><span class="sxs-lookup"><span data-stu-id="4dd3e-116">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms.</span></span> <span data-ttu-id="4dd3e-117">系統管理員必須註冊他們想要允許系統中的增益集。</span><span class="sxs-lookup"><span data-stu-id="4dd3e-117">Administrators must register the add-ins that they want to allow in the system.</span></span> <span data-ttu-id="4dd3e-118">聊天室管理員及建立者可以選擇從允許的增益集至其各自的會議室最相關的清單。</span><span class="sxs-lookup"><span data-stu-id="4dd3e-118">Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4dd3e-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4dd3e-119">See Also</span></span>


[<span data-ttu-id="4dd3e-120">管理類別、 聊天室及 Lync Server 2013 中增益集</span><span class="sxs-lookup"><span data-stu-id="4dd3e-120">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

