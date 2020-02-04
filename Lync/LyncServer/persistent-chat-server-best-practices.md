---
title: 常設聊天室伺服器最佳做法
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
ms.openlocfilehash: 119bc67622928ec2e60f082e72322e7b0b923c2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="d5978-102">常設聊天室伺服器最佳做法</span><span class="sxs-lookup"><span data-stu-id="d5978-102">Persistent Chat Server best practices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5978-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="d5978-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="d5978-104">當您建立類別和持續聊天室並設計您的範圍與成員資格時，下列秘訣可協助您規劃：</span><span class="sxs-lookup"><span data-stu-id="d5978-104">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="d5978-105">如果您的公司不需要具道德的牆，請不要縮小類別樹狀結構中的範圍。</span><span class="sxs-lookup"><span data-stu-id="d5978-105">If your company does not require an ethical wall, do not narrow the scope in your category tree.</span></span> <span data-ttu-id="d5978-106">將所有使用者放在單一類別的範圍內，並建立該類別中的所有聊天室。</span><span class="sxs-lookup"><span data-stu-id="d5978-106">Put all your users in the scope of one category, and create all chat rooms in that category.</span></span> <span data-ttu-id="d5978-107">接著，只使用成員資格清單來准許或限制每個聊天室的存取權。</span><span class="sxs-lookup"><span data-stu-id="d5978-107">Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="d5978-108">在大多數情況下，您應該讓使用者建立新的聊天室，讓您可以隨時開始討論新主題。</span><span class="sxs-lookup"><span data-stu-id="d5978-108">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time.</span></span> <span data-ttu-id="d5978-109">您可以將**製作者**清單製作成與**AllowedMembers**清單相同的方式來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="d5978-109">Do this by making the **Creators** list the same as the **AllowedMembers** list.</span></span> <span data-ttu-id="d5978-110">不過，如果您想要只允許中央支援小組或指定的使用者建立會議室，請將**製作者**清單設為適當的子集。</span><span class="sxs-lookup"><span data-stu-id="d5978-110">However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="d5978-111">為每個聊天室提供完整的名稱和描述摘要，說明其在您的組織中要符合的位置。</span><span class="sxs-lookup"><span data-stu-id="d5978-111">Give each chat room a complete name and description summary that describes where it fits in with your organization.</span></span> <span data-ttu-id="d5978-112">因為使用者使用聊天室時看不到類別名稱，所以您無法依賴類別名稱來協助使用者判斷聊天室的預期論壇。</span><span class="sxs-lookup"><span data-stu-id="d5978-112">Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="d5978-113">如果您有特定的命名慣例或其他存取控制或驗證實現，您可能會想要建立自訂的聊天室建立工作流程。</span><span class="sxs-lookup"><span data-stu-id="d5978-113">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="d5978-114">[持續聊天] 設定可讓您自訂**RoomManagementUrl**給您所裝載的內容。</span><span class="sxs-lookup"><span data-stu-id="d5978-114">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="d5978-115">例如，當使用者按一下 Lync 用戶端中**的 [建立聊天室**] 時，可以將它們重新導向至您的自訂方案。</span><span class="sxs-lookup"><span data-stu-id="d5978-115">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="d5978-116">您可以透過在聊天室中加入其他商務資料，來建立各種增益集，協助改善聊天室的體驗。</span><span class="sxs-lookup"><span data-stu-id="d5978-116">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms.</span></span> <span data-ttu-id="d5978-117">系統管理員必須註冊他們想要在系統中允許的增益集。</span><span class="sxs-lookup"><span data-stu-id="d5978-117">Administrators must register the add-ins that they want to allow in the system.</span></span> <span data-ttu-id="d5978-118">聊天室管理員與創意者可以從允許的增益集清單中選擇與其各自的聊天室最相關的增益集。</span><span class="sxs-lookup"><span data-stu-id="d5978-118">Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d5978-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="d5978-119">See Also</span></span>


[<span data-ttu-id="d5978-120">在 Lync Server 2013 中管理類別、聊天室及增益集</span><span class="sxs-lookup"><span data-stu-id="d5978-120">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

