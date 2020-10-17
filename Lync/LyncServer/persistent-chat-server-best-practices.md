---
title: Persistent Chat Server 最佳作法
description: Persistent Chat Server 最佳作法。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c575c0afa0366e88748eadfcf4c04fccb20b375
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571259"
---
# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="a2cb7-103">Persistent Chat Server 最佳作法</span><span class="sxs-lookup"><span data-stu-id="a2cb7-103">Persistent Chat Server best practices</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2cb7-104">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="a2cb7-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="a2cb7-105">當您建立類別和持續聊天室並設計範圍和成員資格時，下列秘訣可協助您進行規劃：</span><span class="sxs-lookup"><span data-stu-id="a2cb7-105">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="a2cb7-106">如果您的公司不需要道德的留言板，請勿縮小類別樹狀目錄中的範圍。</span><span class="sxs-lookup"><span data-stu-id="a2cb7-106">If your company does not require an ethical wall, do not narrow the scope in your category tree.</span></span> <span data-ttu-id="a2cb7-107">將所有使用者放在一個類別的範圍中，並在該類別中建立所有聊天室。</span><span class="sxs-lookup"><span data-stu-id="a2cb7-107">Put all your users in the scope of one category, and create all chat rooms in that category.</span></span> <span data-ttu-id="a2cb7-108">接著，只使用成員資格清單，授與或限制每個聊天室的存取權。</span><span class="sxs-lookup"><span data-stu-id="a2cb7-108">Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="a2cb7-109">在大多數情況下，您應該讓使用者能夠建立新的聊天室，以便在任何時間開始有關新主題的討論。</span><span class="sxs-lookup"><span data-stu-id="a2cb7-109">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time.</span></span> <span data-ttu-id="a2cb7-110">讓建立 **者** 清單與 **AllowedMembers** 清單相同。</span><span class="sxs-lookup"><span data-stu-id="a2cb7-110">Do this by making the **Creators** list the same as the **AllowedMembers** list.</span></span> <span data-ttu-id="a2cb7-111">不過，如果您只想要讓中央支援小組或指定的使用者建立聊天室，請將建立 **者** 清單當做適當的子集。</span><span class="sxs-lookup"><span data-stu-id="a2cb7-111">However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="a2cb7-112">提供每個聊天室的完整名稱和描述摘要，說明組織中適合的位置。</span><span class="sxs-lookup"><span data-stu-id="a2cb7-112">Give each chat room a complete name and description summary that describes where it fits in with your organization.</span></span> <span data-ttu-id="a2cb7-113">由於使用者在使用聊天室時看不到其類別名稱，因此您無法依賴類別名稱來協助使用者決定聊天室的預定討論論壇。</span><span class="sxs-lookup"><span data-stu-id="a2cb7-113">Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="a2cb7-114">如果您有某些命名慣例或其他的存取控制或驗證實施，您可能想要建立自訂聊天室建立工作流程。</span><span class="sxs-lookup"><span data-stu-id="a2cb7-114">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="a2cb7-115">Persistent Chat 設定可讓您自訂 **RoomManagementUrl** 為您裝載的內容。</span><span class="sxs-lookup"><span data-stu-id="a2cb7-115">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="a2cb7-116">例如，當使用者按一下其 Lync 用戶端中 **的 [建立會議室** ] 時，即可將其重新導向至您的自訂解決方案。</span><span class="sxs-lookup"><span data-stu-id="a2cb7-116">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="a2cb7-117">建立各種增益集，協助您在聊天室中引入其他商務資料，以加強聊天室的體驗。</span><span class="sxs-lookup"><span data-stu-id="a2cb7-117">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms.</span></span> <span data-ttu-id="a2cb7-118">管理員必須在系統中註冊他們想要允許的增益集。</span><span class="sxs-lookup"><span data-stu-id="a2cb7-118">Administrators must register the add-ins that they want to allow in the system.</span></span> <span data-ttu-id="a2cb7-119">聊天室管理員和建立者可以從與其各自的聊天室最相關的現有增益集清單中選擇。</span><span class="sxs-lookup"><span data-stu-id="a2cb7-119">Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a2cb7-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a2cb7-120">See Also</span></span>


[<span data-ttu-id="a2cb7-121">在 Lync Server 2013 中管理類別、聊天室及增益集</span><span class="sxs-lookup"><span data-stu-id="a2cb7-121">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

