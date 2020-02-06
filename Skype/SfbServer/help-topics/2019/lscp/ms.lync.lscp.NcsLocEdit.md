---
title: 位置原則建立新的或編輯現有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以設定位置原則，來判斷是否啟用增強型 9-1-1 (E9-1-1) 及其使用方式，以及針對使用者和連絡人使用位置資訊的方式。
ms.openlocfilehash: b4b67535c318e92ca951deaff167c0d86cc4d2a2
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41792191"
---
# <a name="location-policy-create-new-or-edit-existing"></a><span data-ttu-id="8a6b8-103">位置原則：建立新的或編輯現有原則</span><span class="sxs-lookup"><span data-stu-id="8a6b8-103">Location Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="8a6b8-104">您可以設定位置原則，來判斷是否啟用增強型 9-1-1 (E9-1-1) 及其使用方式，以及針對使用者和連絡人使用位置資訊的方式。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-104">You can configure Location policies to determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="8a6b8-105">UI 參考</span><span class="sxs-lookup"><span data-stu-id="8a6b8-105">UI Reference</span></span>

<span data-ttu-id="8a6b8-106">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="8a6b8-107">**範圍**識別您要建立或修改之位置原則的範圍： [全域]、[網站] 或 [使用者]。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-107">**Scope** Identifies the scope of the location policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="8a6b8-108">**名稱**每個位置原則都需要名稱。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-108">**Name** Each location policy requires a name.</span></span> <span data-ttu-id="8a6b8-109">全域及網站位置原則預設會命名，且無法變更名稱。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-109">Global and site location policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="8a6b8-110">針對使用者位置原則，請使用識別使用者或使用者群組的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-110">For user location policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8a6b8-111">位置原則儲存完畢後，就無法變更其名稱。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-111">After you save the location policy, the name cannot be changed.</span></span>

- <span data-ttu-id="8a6b8-112">**啟用增強型9-1-1 （E9-1-1）** 選取此核取方塊，以針對獲指派此位置原則的使用者啟用 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-112">**Enable Enhanced 9-1-1 (E9-1-1)** Select this check box to enable E9-1-1 for users who are assigned this location policy.</span></span>

- <span data-ttu-id="8a6b8-113">**位置**指定是否提示使用者輸入位置資訊：</span><span class="sxs-lookup"><span data-stu-id="8a6b8-113">**Location** Specify whether users are prompted for location information:</span></span>

  - <span data-ttu-id="8a6b8-114">**必要**如果使用者在新位置註冊時，系統會提示使用者輸入位置資訊，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-114">**Required** Select this option if users are to be prompted for location information when their client registers at a new location.</span></span> <span data-ttu-id="8a6b8-115">使用者可以在不輸入位置資訊的情況下關閉提示。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-115">Users can dismiss the prompt without entering location information.</span></span>

  - <span data-ttu-id="8a6b8-116">**不需要**如果系統不會提示使用者輸入位置資訊，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-116">**Not required** Select this option if users are not to be prompted for location information.</span></span>

  - <span data-ttu-id="8a6b8-117">**免責聲明**如果系統會提示使用者輸入位置資訊，請選取此選項，但如果他們拒絕提示而不輸入資訊，就會看到免責聲明訊息。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-117">**Disclaimer** Select this option if users are to be prompted for location information, but will see a disclaimer message if they decline the prompt without entering the information.</span></span> <span data-ttu-id="8a6b8-118">使用者可以完成緊急通話，但不能撥打電話給他們輸入位置資訊。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-118">Users can complete an emergency call but no other calls until they enter the location information.</span></span>

- <span data-ttu-id="8a6b8-119">**僅使用 E9 的位置-1-1-1**如果位置資訊僅用於緊急通話，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-119">**Use location for E9-1-1 only** Select this check box if location information is to be used only for emergency calls.</span></span>

- <span data-ttu-id="8a6b8-120">**PSTN 使用量**選取將用來判斷哪種語音路線將用來從使用這個設定檔之用戶端傳送緊急通話的公用交換電話網絡（PSTN）用法。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-120">**PSTN usage** Select the public switched telephone network (PSTN) usage that will be used to determine which voice route will be used for routing emergency calls from clients that use this profile.</span></span> <span data-ttu-id="8a6b8-121">與此使用相關聯的路線應該指向專用於緊急通話的 SIP 幹線，或指向將緊急呼叫路由到最接近的公用安全應答點（PSAP）的緊急位置識別號碼（ELIN）閘道。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-121">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="8a6b8-122">選項包括**內部**、**本機**或**遠距離**。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-122">Options are **Internal**, **Local**, or **Long distance**.</span></span>

- <span data-ttu-id="8a6b8-123">**E9-1-1 撥打號碼**指定要撥打緊急服務的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-123">**E9-1-1 dial number** Specify the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="8a6b8-124">**E9-1-1 撥號遮罩**指定使用者撥號的號碼，然後將它轉換成緊急電話撥號碼。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-124">**E9-1-1 dial mask** Specify a number that a user dials, which is then translated into the emergency dial number.</span></span> <span data-ttu-id="8a6b8-125">例如，在這個欄位中輸入212的值，讓使用者可以撥號到212來取得緊急服務。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-125">For example, enter a value of 212 in this field so that a user can dial 212 to reach emergency services.</span></span> <span data-ttu-id="8a6b8-126">這可讓您撥打備用的緊急電話號碼，而且仍能撥打電話給緊急服務（例如，如果某個國家或地區有不同緊急號碼的人嘗試撥打該國家或地區的號碼，而不是他們目前所在的國家或地區）。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-126">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region's number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="8a6b8-127">您可以使用分號來分隔值，以定義多個緊急撥號遮罩。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-127">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="8a6b8-128">例如，212; 414。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-128">For example, 212;414.</span></span> <span data-ttu-id="8a6b8-129">字串的最大長度為100個字元。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-129">The maximum length of the string is 100 characters.</span></span> <span data-ttu-id="8a6b8-130">每個字元都必須是數位0到9。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-130">Each character must be a digit 0 through 9.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8a6b8-131">請確保撥號遮罩與通話駐留號碼範圍中的數字不同，因為通話駐留路由會優先於緊急撥號字串轉換。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-131">Make sure that the dial mask is not the same as a number in a call park number range, because call park routing takes precedence over emergency dial string conversion.</span></span> <span data-ttu-id="8a6b8-132">若要查看通話公園編號範圍，請按一下左側導覽列中的 [**語音功能**]，然後按一下 [**通話駐留**]。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-132">To see the Call Park number ranges, click **Voice Features** in the left navigation bar, and then click **Call Park**.</span></span>

- <span data-ttu-id="8a6b8-133">**通知 URI**指定一個或多個 SIP Uri，以便在進行緊急通話時收到通知。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-133">**Notification URI** Specify one or more SIP URIs to be notified when an emergency call is made.</span></span> <span data-ttu-id="8a6b8-134">例如，輸入公司安全性 office 的 SIP URI，即可在進行緊急呼叫時，以立即訊息通知安全員工。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-134">For example, type the company security office's SIP URI to notify security staff with an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="8a6b8-135">如果來電者的位置可用，就會在通知中包含該位置。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-135">If the caller's location is available, the location is included in the notification.</span></span> <span data-ttu-id="8a6b8-136">您可以將多個 SIP Uri 指定為以逗號分隔的清單。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-136">You can specify multiple SIP URIs as a comma-separated list.</span></span> <span data-ttu-id="8a6b8-137">例如，"sip： security@litwareinc .com"，"sip： kmyer@litwareinc .com"。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-137">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="8a6b8-138">字串的長度必須是1到256個字元，且必須以前置詞「sip：」開頭。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-138">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="8a6b8-139">您也可以指定通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-139">You can also specify distribution lists.</span></span>

- <span data-ttu-id="8a6b8-140">**會議 URI**針對協力廠商，指定要 conferenced 緊急通話的 SIP URI （在此案例中為電話號碼）。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-140">**Conference URI** Specify the SIP URI (telephone number, in this case) for a third party to be conferenced in to emergency calls.</span></span> <span data-ttu-id="8a6b8-141">例如，輸入公司安全性辦公室的電話號碼，讓他們在進行緊急通話時接聽來電。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-141">For example, type the company security office's phone number so that they receive a call when an emergency call is made.</span></span> <span data-ttu-id="8a6b8-142">[**會議模式]** 的設定會決定協力廠商是否可以參與或直接接聽通話。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-142">The setting for **Conference mode** determines whether the third party can participate or just listen in to the call.</span></span> <span data-ttu-id="8a6b8-143">字串必須是介於1到256個字元的長度，且必須以前置詞 sip 開頭：。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-143">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span>

- <span data-ttu-id="8a6b8-144">**會議模式**如果您已指定**會議 URI**的值，請將此欄位設定為下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="8a6b8-144">**Conference mode** If you specified a value for **Conference URI**, set this field to one of the following values:</span></span>

  - <span data-ttu-id="8a6b8-145">**單向**指定協力廠商只能接聽來電者與 PSAP 操作員之間的通話。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-145">**One-way** Specifies that the third party can only listen in to the call between the caller and the PSAP operator.</span></span>

  - <span data-ttu-id="8a6b8-146">**雙向**指定協力廠商可以參與呼叫者與 PSAP 操作員之間的通話。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-146">**Two-way** Specifies that the third party can participate in the call between the caller and the PSAP operator.</span></span>

<span data-ttu-id="8a6b8-147">如需企業語音緊急服務功能和功能的詳細資訊，請參閱規劃檔中的[E9-1-](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) 1。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-147">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="8a6b8-148">如需使用位置原則的詳細資訊，請參閱作業文件中的〈[Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="8a6b8-148">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


