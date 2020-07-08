---
title: Microsoft 團隊的溝通合規性
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: 瞭解溝通合規性，從 Microsoft 小組角度來看「測試人員風險」方案解決方案集的一部分（這是 M365 通訊合規性功能的一部分）。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf97f4adc33b0855e986cf2baed54f69de91f4f0
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077689"
---
# <a name="communication-compliance-for-microsoft-teams"></a><span data-ttu-id="0802c-103">Microsoft 團隊的溝通合規性</span><span class="sxs-lookup"><span data-stu-id="0802c-103">Communication compliance for Microsoft Teams</span></span>

<span data-ttu-id="0802c-104">[溝通合規性] 是 Microsoft 365 中新的「測試人員-風險」方案集合的一部分，可協助您偵測、捕獲並修正組織中不適當的訊息，以協助將通訊風險降到最低。</span><span class="sxs-lookup"><span data-stu-id="0802c-104">Communication compliance is part of the new insider risk solution set in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and take remediation actions for inappropriate messages in your organization.</span></span> <span data-ttu-id="0802c-105">在小組頻道或1:1 和群組聊天中，協助識別冒犯性語言與反騷擾。</span><span class="sxs-lookup"><span data-stu-id="0802c-105">It helps in identifying Offensive language and anti-harassment in Team Channels or 1:1 and Group chats.</span></span> <span data-ttu-id="0802c-106">您也可以設定原則，以查看是否有任何機密資訊是在小組通道或1:1 和群組聊天中共用。</span><span class="sxs-lookup"><span data-stu-id="0802c-106">You can also set policies to see if any Sensitive information is being shared as part of Team channels or 1:1 and Group chats.</span></span> <span data-ttu-id="0802c-107">如需不同類型的原則以及如何設定的詳細資訊，請參閱[M365 文章](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)。</span><span class="sxs-lookup"><span data-stu-id="0802c-107">For more information on different types of policies and how to set up refer to the [M365 article](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-teams"></a><span data-ttu-id="0802c-108">如何在團隊中使用溝通合規性</span><span class="sxs-lookup"><span data-stu-id="0802c-108">How to use communication compliance in Teams</span></span>

### <a name="identify-inappropriate-messages"></a><span data-ttu-id="0802c-109">找出不適當的訊息</span><span class="sxs-lookup"><span data-stu-id="0802c-109">Identify inappropriate messages</span></span>

<span data-ttu-id="0802c-110">如果您想要識別任何在 Microsoft 團隊（1:1、群組聊天或頻道交談）中傳送的訊息，包括冒犯性語言或反騷擾，您可以啟用原則來識別這項訊息，並採取必要步驟，例如傳送訓練資料或升級至正確的主管機構。</span><span class="sxs-lookup"><span data-stu-id="0802c-110">If you want to identify any messages that are sent in Microsoft Teams (1:1, Group Chats or Channel conversations) contain Offensive Language or anti-harassment, you can enable policies to identify this and the reviewer can look into the messages and take necessary steps like sending training material or escalate to the right authorities.</span></span>

### <a name="identify-sensitive-or-regulatory-information"></a><span data-ttu-id="0802c-111">找出機密或法規資訊</span><span class="sxs-lookup"><span data-stu-id="0802c-111">Identify sensitive or Regulatory information</span></span>

<span data-ttu-id="0802c-112">如果您想要掃描 Microsoft 團隊（1:1、群組聊天或頻道交談）中傳送的郵件，瞭解機密資訊或法規類型，您可以選擇支援預先定義的機密或法規類型的原則。</span><span class="sxs-lookup"><span data-stu-id="0802c-112">If you want to scan messages sent in Microsoft Teams (1:1, Group Chats or Channel conversations) for sensitive information or regulatory types, you can choose policies that support predefined sensitive or regulatory types.</span></span>

> [!NOTE]
> <span data-ttu-id="0802c-113">通訊合規性不支援專用通道。</span><span class="sxs-lookup"><span data-stu-id="0802c-113">Private channels are not supported by communication compliance.</span></span>

### <a name="custom-policy"></a><span data-ttu-id="0802c-114">自訂原則</span><span class="sxs-lookup"><span data-stu-id="0802c-114">Custom Policy</span></span>

<span data-ttu-id="0802c-115">您可以使用此範本來設定特定通訊通道、個別偵測條件，以及在您的組織中監視及審查的內容量。</span><span class="sxs-lookup"><span data-stu-id="0802c-115">Use this template to configure specific communication channels, individual detection conditions, and the amount of content to monitor and review in your organization.</span></span>

### <a name="custom-trainable-classifier"></a><span data-ttu-id="0802c-116">自訂 Trainable 分類器</span><span class="sxs-lookup"><span data-stu-id="0802c-116">Custom Trainable classifier</span></span>

<span data-ttu-id="0802c-117">當某個現成的分類器不符合您的需求時，請使用 trainable 分類器。</span><span class="sxs-lookup"><span data-stu-id="0802c-117">Use trainable classifiers when one of the out of the box classifiers won't meet your needs.</span></span> <span data-ttu-id="0802c-118">Microsoft 365 分類器是一種工具，可讓您訓練來辨識各種類型的內容，方法是提供其範例來查看。</span><span class="sxs-lookup"><span data-stu-id="0802c-118">A Microsoft 365 classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="0802c-119">訓練分類器首先要提供人工挑選的範例，並正確符合類別。</span><span class="sxs-lookup"><span data-stu-id="0802c-119">Training the classifier involves first giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="0802c-120">然後，在處理完這些範例之後，請為其提供混合使用正和負樣本的方式來測試預測。</span><span class="sxs-lookup"><span data-stu-id="0802c-120">Then, after it has processed those samples, you test the predictions by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="0802c-121">若要進一步瞭解此話題，請參閱[M365 文章](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier)，以取得本主題的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0802c-121">To Lean more about this refer to the [M365 article](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) for more on this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="0802c-122">溝通合規性現在支援 Exchange 混合式部署。</span><span class="sxs-lookup"><span data-stu-id="0802c-122">Communication compliance now supports Exchange hybrid deployments.</span></span>

<span data-ttu-id="0802c-123">通訊合規性支援與原則相符之任何訊息的交談歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="0802c-123">Communication compliance supports conversation history for any messages that match the polices.</span></span> <span data-ttu-id="0802c-124">這會提供調查管理員的相關內容。</span><span class="sxs-lookup"><span data-stu-id="0802c-124">This provides context to the investigating admin.</span></span>

:::image type="content" source="media/communication-compliance-1.png" alt-text="Microsoft 團隊中的通訊合規性畫面。":::

## <a name="where-communication-policies-can-be-applied-in-teams"></a><span data-ttu-id="0802c-126">可在團隊中套用通訊原則的位置</span><span class="sxs-lookup"><span data-stu-id="0802c-126">Where communication policies can be applied in Teams</span></span>

<span data-ttu-id="0802c-127">您可以針對在小組中傳送的訊息設定通訊合規性原則，其層級如下：</span><span class="sxs-lookup"><span data-stu-id="0802c-127">Communication compliance policies can be setup for messages sent in Teams at the following levels:</span></span>

- <span data-ttu-id="0802c-128">使用者層級：管理員可以在個別使用者層級設定原則，或將原則套用到租使用者上的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="0802c-128">User level : An admin can set up policies at an individual user level or apply it to all the users on the tenant.</span></span> <span data-ttu-id="0802c-129">這只會涵蓋使用者在1:1 或群組聊天中傳送的訊息。</span><span class="sxs-lookup"><span data-stu-id="0802c-129">This will only covers messages that a user sent in 1:1 or Group chats.</span></span>
- <span data-ttu-id="0802c-130">小組層次：管理員也可以在小組上設定原則。</span><span class="sxs-lookup"><span data-stu-id="0802c-130">Team Level: An admin can also set up policies on a team.</span></span> <span data-ttu-id="0802c-131">這涵蓋該小組中該頻道所傳送的所有訊息（不支援專用通道訊息）。</span><span class="sxs-lookup"><span data-stu-id="0802c-131">This covers all the messages sent in the channel in that team (Private channel messages are not supported).</span></span>
