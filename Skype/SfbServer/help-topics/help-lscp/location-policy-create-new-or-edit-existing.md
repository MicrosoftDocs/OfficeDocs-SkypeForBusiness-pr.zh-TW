---
title: 位置原則建立新的或編輯現有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
description: 您可以設定位置原則，以判斷是否已啟用增強型 9-1-1 (E9-1-1) ，以及如何使用位置資訊，以及使用者和連絡人的使用方式。
ms.openlocfilehash: f171d841ec68b3e0b0b4f7c8b9d374ff2261d149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803963"
---
# <a name="location-policy-create-new-or-edit-existing"></a><span data-ttu-id="eb65b-103">位置原則：建立新的或編輯現有原則</span><span class="sxs-lookup"><span data-stu-id="eb65b-103">Location Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="eb65b-104">您可以設定位置原則，以判斷是否已啟用增強型 9-1-1 (E9-1-1) ，以及如何使用位置資訊，以及使用者和連絡人的使用方式。</span><span class="sxs-lookup"><span data-stu-id="eb65b-104">You can configure Location policies to determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="eb65b-105">UI 參考</span><span class="sxs-lookup"><span data-stu-id="eb65b-105">UI Reference</span></span>

<span data-ttu-id="eb65b-106">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="eb65b-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="eb65b-107">**範圍** 識別您要建立或修改之位置原則的範圍：全域、網站或使用者。</span><span class="sxs-lookup"><span data-stu-id="eb65b-107">**Scope** Identifies the scope of the location policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="eb65b-108">**名稱** 每個位置原則都需要名稱。</span><span class="sxs-lookup"><span data-stu-id="eb65b-108">**Name** Each location policy requires a name.</span></span> <span data-ttu-id="eb65b-109">全域及網站位置原則的命名依預設值，且無法變更名稱。</span><span class="sxs-lookup"><span data-stu-id="eb65b-109">Global and site location policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="eb65b-110">針對使用者位置原則，請使用識別使用者或使用者群組的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="eb65b-110">For user location policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eb65b-111">在您儲存位置原則之後，就無法變更此名稱。</span><span class="sxs-lookup"><span data-stu-id="eb65b-111">After you save the location policy, the name cannot be changed.</span></span>

- <span data-ttu-id="eb65b-112">**啟用增強型 9-1-1 (E9-1-1)** 選取此核取方塊可為指派此位置原則的使用者啟用 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="eb65b-112">**Enable Enhanced 9-1-1 (E9-1-1)** Select this check box to enable E9-1-1 for users who are assigned this location policy.</span></span>

- <span data-ttu-id="eb65b-113">**位置** 指定是否提示使用者輸入位置資訊：</span><span class="sxs-lookup"><span data-stu-id="eb65b-113">**Location** Specify whether users are prompted for location information:</span></span>

  - <span data-ttu-id="eb65b-114">**必要** 如果使用者在其用戶端註冊新位置時，系統會提示使用者輸入位置資訊，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="eb65b-114">**Required** Select this option if users are to be prompted for location information when their client registers at a new location.</span></span> <span data-ttu-id="eb65b-115">使用者可以在不輸入位置資訊的情況下關閉提示。</span><span class="sxs-lookup"><span data-stu-id="eb65b-115">Users can dismiss the prompt without entering location information.</span></span>

  - <span data-ttu-id="eb65b-116">**不需要** 如果不提示使用者輸入位置資訊，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="eb65b-116">**Not required** Select this option if users are not to be prompted for location information.</span></span>

  - <span data-ttu-id="eb65b-117">**免責聲明** 如果系統提示使用者輸入位置資訊，請選取此選項，但如果不輸入資訊，就會看到免責聲明訊息。</span><span class="sxs-lookup"><span data-stu-id="eb65b-117">**Disclaimer** Select this option if users are to be prompted for location information, but will see a disclaimer message if they decline the prompt without entering the information.</span></span> <span data-ttu-id="eb65b-118">使用者可以完成緊急通話，但不能撥打其他電話，直到他們輸入位置資訊為止。</span><span class="sxs-lookup"><span data-stu-id="eb65b-118">Users can complete an emergency call but no other calls until they enter the location information.</span></span>

- <span data-ttu-id="eb65b-119">**僅針對 E9-1-1 使用位置** 如果 location 資訊只用于緊急通話，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="eb65b-119">**Use location for E9-1-1 only** Select this check box if location information is to be used only for emergency calls.</span></span>

- <span data-ttu-id="eb65b-120">**PSTN 使用** 方式選取公用交換電話網路 (PSTN) 使用方式，以決定使用此設定檔之用戶端路由傳送緊急通話時所使用的語音路由。</span><span class="sxs-lookup"><span data-stu-id="eb65b-120">**PSTN usage** Select the public switched telephone network (PSTN) usage that will be used to determine which voice route will be used for routing emergency calls from clients that use this profile.</span></span> <span data-ttu-id="eb65b-121">與此使用方式關聯的路由應該指向緊急通話專用的 SIP 主幹，或緊急位置識別號碼 (ELIN) 閘道，可將緊急通話路由傳送至最近的公用安全回復點 (PSAP) 。</span><span class="sxs-lookup"><span data-stu-id="eb65b-121">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="eb65b-122">選項包括 **內部**、 **本機** 或 **長距離**。</span><span class="sxs-lookup"><span data-stu-id="eb65b-122">Options are **Internal**, **Local**, or **Long distance**.</span></span>

- <span data-ttu-id="eb65b-123">**E9-1-1 撥號號碼** 指定要撥通緊急服務的號碼。</span><span class="sxs-lookup"><span data-stu-id="eb65b-123">**E9-1-1 dial number** Specify the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="eb65b-124">**E9-1-1 撥號遮罩** 指定使用者撥號的號碼，然後將它轉譯成緊急撥號號碼。</span><span class="sxs-lookup"><span data-stu-id="eb65b-124">**E9-1-1 dial mask** Specify a number that a user dials, which is then translated into the emergency dial number.</span></span> <span data-ttu-id="eb65b-125">例如，在此欄位中輸入212的值，讓使用者可以撥號212以到達緊急服務。</span><span class="sxs-lookup"><span data-stu-id="eb65b-125">For example, enter a value of 212 in this field so that a user can dial 212 to reach emergency services.</span></span> <span data-ttu-id="eb65b-126">這可讓您撥打備用的緊急號碼，並且仍然可以撥打緊急服務 (例如，如果來自國家或地區具有不同緊急號碼的某人嘗試撥打該國家或地區的號碼，而不是其目前在) 中的國家或地區號碼。</span><span class="sxs-lookup"><span data-stu-id="eb65b-126">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region's number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="eb65b-127">您可以使用分號分隔多個值，藉此定義多組緊急撥話遮罩。</span><span class="sxs-lookup"><span data-stu-id="eb65b-127">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="eb65b-128">例如，212; 414。</span><span class="sxs-lookup"><span data-stu-id="eb65b-128">For example, 212;414.</span></span> <span data-ttu-id="eb65b-129">字串的最大長度為 100 個字元。</span><span class="sxs-lookup"><span data-stu-id="eb65b-129">The maximum length of the string is 100 characters.</span></span> <span data-ttu-id="eb65b-130">每個字元必須是 0 到 9 的數字。</span><span class="sxs-lookup"><span data-stu-id="eb65b-130">Each character must be a digit 0 through 9.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="eb65b-131">請確定撥號遮罩與通話駐留號碼範圍中的號碼不同，因為通話駐留路由會優先于緊急撥號字串轉換。</span><span class="sxs-lookup"><span data-stu-id="eb65b-131">Make sure that the dial mask is not the same as a number in a call park number range, because call park routing takes precedence over emergency dial string conversion.</span></span> <span data-ttu-id="eb65b-132">若要查看通話駐留號碼範圍，請按一下左導覽列中的 [ **語音功能** ]，然後按一下 [ **通話駐留**]。</span><span class="sxs-lookup"><span data-stu-id="eb65b-132">To see the Call Park number ranges, click **Voice Features** in the left navigation bar, and then click **Call Park**.</span></span>

- <span data-ttu-id="eb65b-133">**通知 URI** 指定在進行緊急通話時所要通知的一或多個 SIP URIs。</span><span class="sxs-lookup"><span data-stu-id="eb65b-133">**Notification URI** Specify one or more SIP URIs to be notified when an emergency call is made.</span></span> <span data-ttu-id="eb65b-134">例如，輸入公司的安全性 office 的 SIP URI，可在每次進行緊急通話時，向安全性人員通報立即訊息。</span><span class="sxs-lookup"><span data-stu-id="eb65b-134">For example, type the company security office's SIP URI to notify security staff with an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="eb65b-135">如果來電者的位置可用，該位置就會包含在通知中。</span><span class="sxs-lookup"><span data-stu-id="eb65b-135">If the caller's location is available, the location is included in the notification.</span></span> <span data-ttu-id="eb65b-136">您可以將多個 SIP URIs 指定為以逗號分隔的清單。</span><span class="sxs-lookup"><span data-stu-id="eb65b-136">You can specify multiple SIP URIs as a comma-separated list.</span></span> <span data-ttu-id="eb65b-137">例如，"sip： security@litwareinc .com"，"sip： kmyer@litwareinc .com"。</span><span class="sxs-lookup"><span data-stu-id="eb65b-137">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="eb65b-138">字串長度必須介於1到256個字元之間，且必須以前置詞 "sip：" 開頭。</span><span class="sxs-lookup"><span data-stu-id="eb65b-138">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="eb65b-139">您也可以指定通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="eb65b-139">You can also specify distribution lists.</span></span>

- <span data-ttu-id="eb65b-140">**會議 URI** 指定 SIP URI (電話號碼，在此案例中) 協力廠商可警衛至緊急通話。</span><span class="sxs-lookup"><span data-stu-id="eb65b-140">**Conference URI** Specify the SIP URI (telephone number, in this case) for a third party to be conferenced in to emergency calls.</span></span> <span data-ttu-id="eb65b-141">例如，輸入公司的安全性辦公室的電話號碼，以便撥打緊急電話時他們會收到來電。</span><span class="sxs-lookup"><span data-stu-id="eb65b-141">For example, type the company security office's phone number so that they receive a call when an emergency call is made.</span></span> <span data-ttu-id="eb65b-142">[ **會議模式]** 的設定會決定協力廠商是否可以參與或只接聽通話。</span><span class="sxs-lookup"><span data-stu-id="eb65b-142">The setting for **Conference mode** determines whether the third party can participate or just listen in to the call.</span></span> <span data-ttu-id="eb65b-143">字串長度必須為 1 到 256 字元，且開頭必須為首碼 sip:。</span><span class="sxs-lookup"><span data-stu-id="eb65b-143">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span>

- <span data-ttu-id="eb65b-144">**會議模式** 如果您指定了 [ **會議 URI**] 的值，請將此欄位設為下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="eb65b-144">**Conference mode** If you specified a value for **Conference URI**, set this field to one of the following values:</span></span>

  - <span data-ttu-id="eb65b-145">**單向** 指定協力廠商只能接聽來電者與 PSAP 操作員之間的呼叫。</span><span class="sxs-lookup"><span data-stu-id="eb65b-145">**One-way** Specifies that the third party can only listen in to the call between the caller and the PSAP operator.</span></span>

  - <span data-ttu-id="eb65b-146">**雙向** 指定協力廠商可以參與呼叫方和 PSAP 操作員之間的呼叫。</span><span class="sxs-lookup"><span data-stu-id="eb65b-146">**Two-way** Specifies that the third party can participate in the call between the caller and the PSAP operator.</span></span>

<span data-ttu-id="eb65b-147">如需有關 Enterprise Voice 急診 service 功能及功能的詳細資訊，請參閱規劃檔中的 [E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="eb65b-147">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="eb65b-148">如需使用位置原則的詳細資訊，請參閱作業文件中的＜[Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)＞。</span><span class="sxs-lookup"><span data-stu-id="eb65b-148">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


