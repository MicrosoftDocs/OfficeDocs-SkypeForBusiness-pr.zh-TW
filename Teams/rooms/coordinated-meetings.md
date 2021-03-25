---
title: 使用 Microsoft Teams 會議室和 Surface Hub 設定協調的會議
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 設定 Teams 會議室裝置和 Surface Hub，以在一或另一個裝置加入會議時加入會議。
ms.openlocfilehash: 57dc91e4a7d923e218cd1f8f6f0ce22679d550e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117561"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a><span data-ttu-id="03023-103">使用 Microsoft Teams 會議室和 Surface Hub 設定協調會議</span><span class="sxs-lookup"><span data-stu-id="03023-103">Set up Coordinated Meetings with Microsoft Teams Rooms and Surface Hub</span></span>

<span data-ttu-id="03023-104">如果您在會議室中擁有一或多個 Microsoft Teams 會議室裝置或 Surface Hub，您可以設定協調會議。</span><span class="sxs-lookup"><span data-stu-id="03023-104">If you have one or more Microsoft Teams Rooms devices or Surface Hubs in a meeting room, you can set up Coordinated Meetings.</span></span> <span data-ttu-id="03023-105">協調會議可讓您設定 Teams 會議室裝置和 Surface Hub，這樣當您在一個裝置上加入會議時，會議室中的其他裝置也會加入同一個會議。</span><span class="sxs-lookup"><span data-stu-id="03023-105">Coordinated Meetings lets you set up your Teams Rooms devices and Surface Hubs so that when you join a meeting on one device, the other devices in the room are also joined to the same meeting.</span></span> <span data-ttu-id="03023-106">您可以設定攝影機、喇叭和麥克風，讓參與者能夠獲得最佳體驗，而其他人則停用。</span><span class="sxs-lookup"><span data-stu-id="03023-106">You can configure your cameras, speakers, and microphones so that the ones that give participants the best experience are enabled while others are disabled.</span></span> <span data-ttu-id="03023-107">這可避免參與者在將多個裝置新加入會議時，可能遇到令人驚驚的回音和意見回應雜訊。</span><span class="sxs-lookup"><span data-stu-id="03023-107">This avoids the dreaded echo and feedback noise participants can experience when adding multiple devices to a meeting.</span></span>

<span data-ttu-id="03023-108">若要設定協調會議，您必須確定您的 Teams 會議室裝置和 Surface Hub 已正確設定為參與會議。</span><span class="sxs-lookup"><span data-stu-id="03023-108">To set up Coordinated Meetings, you need to make sure your Teams Rooms devices and Surface Hubs are already correctly configured to participate in meetings.</span></span> <span data-ttu-id="03023-109">最重要的是，每個裝置都需要有自己的 Exchange 會議室信箱。</span><span class="sxs-lookup"><span data-stu-id="03023-109">Most importantly, each device needs to have its own Exchange room mailbox.</span></span> <span data-ttu-id="03023-110">若要瞭解如何設定，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="03023-110">For information on how to set them up, see the following articles:</span></span>

- [<span data-ttu-id="03023-111">部署 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="03023-111">Deploy Microsoft Teams Rooms</span></span>](../rooms/rooms-deploy.md)
- [<span data-ttu-id="03023-112">建立 Surface Hub 2S 裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="03023-112">Create Surface Hub 2S device account</span></span>](/surface-hub/surface-hub-2s-account)

<span data-ttu-id="03023-113">確認 Teams 會議室裝置和 Surface Hub 可自動接受會議並成功加入會議之後，您可以設定協調會議。</span><span class="sxs-lookup"><span data-stu-id="03023-113">After you've confirmed that your Teams Rooms devices and Surface Hubs can automatically accept meetings and join them successfully, you can set up Coordinated Meetings.</span></span>

<span data-ttu-id="03023-114">每個會議室應分別完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="03023-114">The following steps should be completed for each meeting room separately.</span></span> <span data-ttu-id="03023-115">一個會議室中的裝置不應設定為與其他會議室中的裝置進行協調會議。</span><span class="sxs-lookup"><span data-stu-id="03023-115">Devices in one meeting room shouldn't be set up for Coordinated Meetings with devices in other meeting rooms.</span></span>

## <a name="step-1-plan-your-coordinated-meeting-experience"></a><span data-ttu-id="03023-116">步驟 1：規劃您的協調會議體驗</span><span class="sxs-lookup"><span data-stu-id="03023-116">Step 1: Plan your Coordinated Meeting experience</span></span>

<span data-ttu-id="03023-117">進行任何組組變更之前，您必須決定哪些裝置會在每個會議室中執行什麼操作。</span><span class="sxs-lookup"><span data-stu-id="03023-117">Before you make any configuration changes, you need to decide which devices will do what in each meeting room.</span></span> <span data-ttu-id="03023-118">也就是說，對於一個給定的會議室，您必須決定哪個裝置會擁有使用中麥克風、相機和白板。</span><span class="sxs-lookup"><span data-stu-id="03023-118">That is, for a given meeting room, you need to decide which device will have the active microphone, camera, and whiteboard.</span></span> <span data-ttu-id="03023-119">您設定裝置的方式取決於您的特定環境，但以下是一些一般建議，請從以下開始著手：</span><span class="sxs-lookup"><span data-stu-id="03023-119">How you configure your devices depends on your specific environment, but here are some general recommendations to start with:</span></span>

- <span data-ttu-id="03023-120">**麥克風** Teams 會議室裝置</span><span class="sxs-lookup"><span data-stu-id="03023-120">**Microphone** Teams Rooms device</span></span>
- <span data-ttu-id="03023-121">**相機** Teams 會議室 (預設為開啟，) Surface Hub 預設為關閉 (但參與者可開啟) </span><span class="sxs-lookup"><span data-stu-id="03023-121">**Camera** Teams Rooms device (on by default) and Surface Hub (off by default, but allowed to be turned on by participants)</span></span>
- <span data-ttu-id="03023-122">**Whiteboard** Surface Hub</span><span class="sxs-lookup"><span data-stu-id="03023-122">**Whiteboard** Surface Hub</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03023-123">請確定您只在一部裝置上啟用麥克風。</span><span class="sxs-lookup"><span data-stu-id="03023-123">Make sure you enable the microphone only on one device.</span></span> <span data-ttu-id="03023-124">如果您在一部以上裝置上啟用，就會聽到音訊回音和意見回應。</span><span class="sxs-lookup"><span data-stu-id="03023-124">If you enable it on more than one device, you'll experience audio echo and feedback.</span></span>

## <a name="step-2-get-your-devices-upns"></a><span data-ttu-id="03023-125">步驟 2：取得您裝置 UPNs</span><span class="sxs-lookup"><span data-stu-id="03023-125">Step 2: Get your devices' UPNs</span></span>

<span data-ttu-id="03023-126">當您在會議室中設定協調會議體驗時，您必須告知該會議室中的 Teams 會議室裝置和 Surface Hub，以協調哪些裝置。</span><span class="sxs-lookup"><span data-stu-id="03023-126">When you set up a Coordinated Meeting experience in a meeting room, you need to tell the Teams Rooms devices and Surface Hubs in that room which devices to coordinate with.</span></span> <span data-ttu-id="03023-127">若要這麼做，在 UPN (UPN) 應該協調其配置的裝置上新增使用者主體名稱。</span><span class="sxs-lookup"><span data-stu-id="03023-127">This is done by adding the user principal name (UPN) of the devices it should coordinate with to its configuration.</span></span> <span data-ttu-id="03023-128">如果您不知道要設定為協調會議之每個裝置使用的 UPNs，您可以使用 Microsoft 365 系統管理中心找到它們。</span><span class="sxs-lookup"><span data-stu-id="03023-128">If you don't know the UPNs for each of the devices you want to set up for Coordinated Meetings, you can find them using the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="03023-129">您必須指派系統管理員角色才能存取 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="03023-129">You need to be assigned an admin role to access the Microsoft 365 admin center.</span></span> <span data-ttu-id="03023-130">詳細資訊，請參閱 [關於系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="03023-130">For more information, see [About admin roles](/microsoft-365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="03023-131">若要取得 Teams 會議室裝置和 Surface Hub 的 UPNs，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="03023-131">To get the UPNs of your Teams Rooms devices and Surface Hubs, do the following:</span></span>

1. <span data-ttu-id="03023-132">請流覽 來登錄 Microsoft 365 系統管理中心 https://admin.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="03023-132">Sign in to the Microsoft 365 admin center by visiting https://admin.microsoft.com.</span></span>
2. <span data-ttu-id="03023-133">前往使用者  >  **活動使用者**。</span><span class="sxs-lookup"><span data-stu-id="03023-133">Go to **Users** > **Active users**.</span></span>
3. <span data-ttu-id="03023-134">在顯示名稱欄中尋找 Teams 會議室裝置或 Surface  Hub 的名稱 (如果您有許多使用者，您可以使用搜尋) 。</span><span class="sxs-lookup"><span data-stu-id="03023-134">Find the name of your Teams Rooms device or Surface Hub in the **Display name** column (you can use the **Search** box if you have many users).</span></span>
4. <span data-ttu-id="03023-135">在使用者名稱欄中尋找UPN (其外觀會類似 alias@contoso.com 或 alias@contoso.onmicrosoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="03023-135">Find the UPN in the **Username** column (it'll look something like alias@contoso.com or alias@contoso.onmicrosoft.com).</span></span>
5. <span data-ttu-id="03023-136">針對將參與協調會議的每個裝置重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="03023-136">Repeat this for each device that will participate in Coordinated Meetings.</span></span>

## <a name="step-3-create-a-deployment-worksheet"></a><span data-ttu-id="03023-137">步驟 3：建立部署工作表</span><span class="sxs-lookup"><span data-stu-id="03023-137">Step 3: Create a deployment worksheet</span></span>

<span data-ttu-id="03023-138">規劃協調會議體驗並收集裝置 UPNs 清單之後，建立部署工作表是一個好方法。</span><span class="sxs-lookup"><span data-stu-id="03023-138">After you've planned your Coordinated Meeting experience and gathered a list of your devices' UPNs, it's a good idea to create a deployment worksheet.</span></span> <span data-ttu-id="03023-139">部署工作表可協助您將您想要設定的所有裝置設定視覺化，讓您驗證您的選擇並檢查錯誤。</span><span class="sxs-lookup"><span data-stu-id="03023-139">A deployment worksheet will help you visualize the configuration you want to set across all of your devices, allowing you to validate your choices and check for errors.</span></span>

<span data-ttu-id="03023-140">在試算表應用程式中，新增第一欄中下列各欄的列：</span><span class="sxs-lookup"><span data-stu-id="03023-140">In a spreadsheet app, add rows for the following in the first column:</span></span>

| <span data-ttu-id="03023-141">設定</span><span class="sxs-lookup"><span data-stu-id="03023-141">Setting</span></span>                | <span data-ttu-id="03023-142">描述</span><span class="sxs-lookup"><span data-stu-id="03023-142">Description</span></span>      |
|------------------------|-----------------|
| <span data-ttu-id="03023-143">**音訊預設值**</span><span class="sxs-lookup"><span data-stu-id="03023-143">**Audio default**</span></span>      | <span data-ttu-id="03023-144">決定會議開始時，麥克風會位於哪個裝置上。</span><span class="sxs-lookup"><span data-stu-id="03023-144">Determines on which device the microphone will be active when a meeting starts.</span></span> <span data-ttu-id="03023-145">只有一 (一般為 Teams 會議室裝置) 可以設定此欄位，而其他裝置則必須設定此欄位，以避免音訊回音和 `true` `false` 意見回應。</span><span class="sxs-lookup"><span data-stu-id="03023-145">Only one device (typically a Teams Rooms device) can have this field set to `true` while the rest of the devices must have this field set to `false` to avoid audio echo and feedback.</span></span>          |
| <span data-ttu-id="03023-146">**音訊已啟用**</span><span class="sxs-lookup"><span data-stu-id="03023-146">**Audio enabled**</span></span>      | <span data-ttu-id="03023-147">決定會議參與者是否可以開啟或關閉麥克風。</span><span class="sxs-lookup"><span data-stu-id="03023-147">Determines whether participants in a meeting can toggle the microphone on or off.</span></span> <span data-ttu-id="03023-148">設定為 **音訊** 預設值的裝置應設定此設定，讓參與者不會不小心開啟麥克風，並造成 `false` 音訊回 `false` 音或意見回應。</span><span class="sxs-lookup"><span data-stu-id="03023-148">Devices on which **Audio default** is set to `false` should have this setting set to `false` so that participants can't accidentally turn on a microphone and cause audio echo or feedback.</span></span><p><span data-ttu-id="03023-149">如果 **音訊預設值** 設為 `true` ，此設定會被忽略，參與者可以將麥克風設為靜音或取消靜音。</span><span class="sxs-lookup"><span data-stu-id="03023-149">If **Audio default** is set to `true`, this setting is ignored and participants can mute or unmute the microphone.</span></span>          |
| <span data-ttu-id="03023-150">**視音訊預設值**</span><span class="sxs-lookup"><span data-stu-id="03023-150">**Video default**</span></span>      | <span data-ttu-id="03023-151">決定會議開始時攝影機會使用哪個裝置。</span><span class="sxs-lookup"><span data-stu-id="03023-151">Determines on which device the camera will be active when a meeting starts.</span></span> <span data-ttu-id="03023-152">為了獲得最佳體驗，我們建議您只將 Teams 會議室裝置設定為 ，而所有其他裝置則設為 `true` `false` 。</span><span class="sxs-lookup"><span data-stu-id="03023-152">For the best experience, we recommend that only the Teams Rooms device be set to `true` while all other devices are set to `false`.</span></span>          |
| <span data-ttu-id="03023-153">**啟用視像**</span><span class="sxs-lookup"><span data-stu-id="03023-153">**Video enabled**</span></span>      | <span data-ttu-id="03023-154">決定會議參與者是否可以開啟或關閉相機。</span><span class="sxs-lookup"><span data-stu-id="03023-154">Determines whether participants in a meeting can toggle the camera on or off.</span></span> <span data-ttu-id="03023-155">您可以在活動參與者想要共用不同視 (，例如參與者使用 Surface Hub 白板或 `true`) 。</span><span class="sxs-lookup"><span data-stu-id="03023-155">You can set this to `true` on any other devices in the event participants want to share different video perspectives (such as if a participant is using the Surface Hub whiteboard).</span></span> <span data-ttu-id="03023-156">如果您不希望參與者在裝置上開啟或關閉相機，請將其設定為 `false` 。</span><span class="sxs-lookup"><span data-stu-id="03023-156">If you don't want participants to turn a camera on or off on a device, set this to `false`.</span></span><p> <span data-ttu-id="03023-157">如果 **視音訊預設值** 設定為 `true` ，此設定會被忽略，參與者可以開啟或關閉相機。</span><span class="sxs-lookup"><span data-stu-id="03023-157">If **Video default** is set to `true`, this setting is ignored and participants can turn the camera on or off.</span></span>         |
| <span data-ttu-id="03023-158">**白板預設值**</span><span class="sxs-lookup"><span data-stu-id="03023-158">**Whiteboard default**</span></span> | <span data-ttu-id="03023-159">決定 Teams 會議室裝置是否會顯示其中一個會議參與者共用的白板。</span><span class="sxs-lookup"><span data-stu-id="03023-159">Determines whether the Teams Rooms device will display a whiteboard shared by one of the meeting participants.</span></span> <span data-ttu-id="03023-160">如果您擁有 Surface Hub 且沒有 Surface Hub，建議您將此選項 `false` `true` 設為 。</span><span class="sxs-lookup"><span data-stu-id="03023-160">We recommend that you set this to `false` if you have a Surface Hub and `true` if you don't have one.</span></span> <span data-ttu-id="03023-161">此設定對 Surface Hub 沒有影響。</span><span class="sxs-lookup"><span data-stu-id="03023-161">This setting has no effect on Surface Hubs.</span></span> <span data-ttu-id="03023-162">Surface Hubs 一定會顯示會議參與者共用的白板。</span><span class="sxs-lookup"><span data-stu-id="03023-162">Surface Hubs will always display a whiteboard shared by meeting participants.</span></span>         |
| <span data-ttu-id="03023-163">**已啟用 Whiteboard**</span><span class="sxs-lookup"><span data-stu-id="03023-163">**Whiteboard enabled**</span></span> | <span data-ttu-id="03023-164">決定會議參與者是否可以開啟或關閉白板。</span><span class="sxs-lookup"><span data-stu-id="03023-164">Determines whether participants in a meeting can toggle the whiteboard on or off.</span></span> <span data-ttu-id="03023-165">如果您不希望參與者在裝置上開啟或關閉白板，請將其設定為 `false` 。</span><span class="sxs-lookup"><span data-stu-id="03023-165">If you don't want participants to turn the whiteboard on or off on a device, set this to `false`.</span></span> <p><span data-ttu-id="03023-166">如果 **Whiteboard 預設** 設定為 `true` ，此設定會被忽略，參與者可以開啟或關閉白板。</span><span class="sxs-lookup"><span data-stu-id="03023-166">If **Whiteboard default** is set to `true`, this setting is ignored and participants can turn the whiteboard on or off.</span></span>
| <span data-ttu-id="03023-167">**信任的帳戶**</span><span class="sxs-lookup"><span data-stu-id="03023-167">**Trusted accounts**</span></span>   | <span data-ttu-id="03023-168">這是每個 Teams 會議室裝置或 Surface Hub 的 UPNs 逗號分隔清單，裝置應接受會議加入邀請，或應該將會議加入邀請寄到哪個位置。</span><span class="sxs-lookup"><span data-stu-id="03023-168">This is a comma-separated list of UPNs for each Teams Room device or Surface Hub that the device should accept meeting join requests from, or to which meeting join requests should be sent.</span></span> |

<span data-ttu-id="03023-169">在後續的欄，新增您的每個 Teams 會議室裝置和 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="03023-169">In subsequent columns, add each of your Teams Rooms devices and Surface Hubs.</span></span> <span data-ttu-id="03023-170">在每一欄中，填寫對應到您想要的會議室體驗的值。</span><span class="sxs-lookup"><span data-stu-id="03023-170">In each column, fill out the values that correspond to the experience you want for the meeting room.</span></span> <span data-ttu-id="03023-171">以下是一個 Teams 會議室裝置和一個 Surface Hub 的範例：</span><span class="sxs-lookup"><span data-stu-id="03023-171">Here's an example with one Teams Rooms device and one Surface Hub:</span></span>

- <span data-ttu-id="03023-172">Teams 裝置</span><span class="sxs-lookup"><span data-stu-id="03023-172">Teams device</span></span>
  - <span data-ttu-id="03023-173">會議開始時 **，音訊和** 視音訊會開啟。</span><span class="sxs-lookup"><span data-stu-id="03023-173">Audio and video are turned **on** when a meeting starts.</span></span> <span data-ttu-id="03023-174">參與者 **可以** 開啟或關閉音訊和視音訊。</span><span class="sxs-lookup"><span data-stu-id="03023-174">Participants **can** toggle audio and video on or off.</span></span>
  - <span data-ttu-id="03023-175">顯示共用白板已關閉。</span><span class="sxs-lookup"><span data-stu-id="03023-175">Displaying a shared whiteboard is turned off.</span></span>
- <span data-ttu-id="03023-176">Surface Hub</span><span class="sxs-lookup"><span data-stu-id="03023-176">Surface Hub</span></span>
  - <span data-ttu-id="03023-177">會議開始時 **音訊** 會關閉。</span><span class="sxs-lookup"><span data-stu-id="03023-177">Audio is turned **off** when a meeting starts.</span></span> <span data-ttu-id="03023-178">參與者 **無法開啟** 或關閉音訊。</span><span class="sxs-lookup"><span data-stu-id="03023-178">Participants **can't** toggle audio on or off.</span></span>
  - <span data-ttu-id="03023-179">會議開始時 **，視** 音訊會關閉。</span><span class="sxs-lookup"><span data-stu-id="03023-179">Video is turned **off** when a meeting starts.</span></span> <span data-ttu-id="03023-180">參與者 **可以** 開啟或關閉視像。</span><span class="sxs-lookup"><span data-stu-id="03023-180">Participants **can** toggle video on or off.</span></span>

| <span data-ttu-id="03023-181">設定</span><span class="sxs-lookup"><span data-stu-id="03023-181">Setting</span></span>                | <span data-ttu-id="03023-182">Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="03023-182">Teams Room</span></span>      | <span data-ttu-id="03023-183">Surface Hub</span><span class="sxs-lookup"><span data-stu-id="03023-183">Surface Hub</span></span>      |
|------------------------|-----------------|------------------|
| <span data-ttu-id="03023-184">**音訊預設值**</span><span class="sxs-lookup"><span data-stu-id="03023-184">**Audio default**</span></span>      | `true`          | `false`          |
| <span data-ttu-id="03023-185">**音訊已啟用**</span><span class="sxs-lookup"><span data-stu-id="03023-185">**Audio enabled**</span></span>      | `true`          | `false`          |
| <span data-ttu-id="03023-186">**視音訊預設值**</span><span class="sxs-lookup"><span data-stu-id="03023-186">**Video default**</span></span>      | `true`          | `false`          |
| <span data-ttu-id="03023-187">**啟用視像**</span><span class="sxs-lookup"><span data-stu-id="03023-187">**Video enabled**</span></span>      | `true`          | `true`           |
| <span data-ttu-id="03023-188">**白板預設值**</span><span class="sxs-lookup"><span data-stu-id="03023-188">**Whiteboard default**</span></span> | `false`         | `false`          |
| <span data-ttu-id="03023-189">**信任的帳戶**</span><span class="sxs-lookup"><span data-stu-id="03023-189">**Trusted accounts**</span></span>   | <span data-ttu-id="03023-190">hub@contoso.com</span><span class="sxs-lookup"><span data-stu-id="03023-190">hub@contoso.com</span></span> | <span data-ttu-id="03023-191">room@contoso.com</span><span class="sxs-lookup"><span data-stu-id="03023-191">room@contoso.com</span></span> |

## <a name="step-4-configure-teams-rooms-device"></a><span data-ttu-id="03023-192">步驟 4：設定 Teams 會議室裝置</span><span class="sxs-lookup"><span data-stu-id="03023-192">Step 4: Configure Teams Rooms device</span></span>

<span data-ttu-id="03023-193">您可以使用裝置觸控式螢幕在 Teams 會議室裝置上設定協調會議，或者如果您需要設定許多裝置，而且想要從中央位置設定，您可以使用 XML 設定檔。</span><span class="sxs-lookup"><span data-stu-id="03023-193">You can either set up Coordinated Meetings on a Teams Rooms device using the device's touch screen or, if you need to set up many devices and want to do so from a central location, you can use an XML configuration file.</span></span>

<span data-ttu-id="03023-194">使用上一個步驟中建立工作表，協助您設定裝置。</span><span class="sxs-lookup"><span data-stu-id="03023-194">Use the worksheet you created in the previous step to help you set up your devices.</span></span>

### <a name="use-the-teams-rooms-devices-touch-screen"></a><span data-ttu-id="03023-195">使用 Teams 會議室裝置觸控式螢幕</span><span class="sxs-lookup"><span data-stu-id="03023-195">Use the Teams Rooms device's touch screen</span></span>

<span data-ttu-id="03023-196">若要在裝置上設定協調會議，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="03023-196">To set up Coordinated Meetings on a device, do the following:</span></span>

1. <span data-ttu-id="03023-197">選取 **...其他**  >  **設定**。</span><span class="sxs-lookup"><span data-stu-id="03023-197">Select **... More** > **Settings**.</span></span>
2. <span data-ttu-id="03023-198">輸入系統管理員密碼，然後選取 **是**。</span><span class="sxs-lookup"><span data-stu-id="03023-198">Enter the Administrator password and select **Yes**.</span></span>
3. <span data-ttu-id="03023-199">選取 **協調會議**。</span><span class="sxs-lookup"><span data-stu-id="03023-199">Select **Coordinated Meetings**.</span></span>
4. <span data-ttu-id="03023-200">在 **選項下**，將 **協調會議設定** 為 _on_。</span><span class="sxs-lookup"><span data-stu-id="03023-200">Under **Options**, set **Coordinated Meeting** to _on_.</span></span>
5. <span data-ttu-id="03023-201">如果 **工作表中的** 音訊預設為 ，請設定開啟此裝置上的 `true` **麥克風** ，否則請將其 _關閉_。</span><span class="sxs-lookup"><span data-stu-id="03023-201">If **Audio default** in your worksheet is `true`, set **Turn on this device's microphone** to on, otherwise leave it _off_.</span></span>
6. <span data-ttu-id="03023-202">如果 **工作表中** 已啟用音訊，請選取在開啟此裝置麥克風下加入會議時允許 `true` **人員啟用**。 </span><span class="sxs-lookup"><span data-stu-id="03023-202">If **Audio enabled** in your worksheet is `true`, select **Let people enable when joining a meeting** under **Turn on this device's microphone**.</span></span> <span data-ttu-id="03023-203">如果開啟此裝置麥克風設為開啟，則無法關閉此選項。</span><span class="sxs-lookup"><span data-stu-id="03023-203">This option can't be turned off if **Turn on this device's microphone** is set to on.</span></span>
7. <span data-ttu-id="03023-204">如果 **工作表中的影片** 預設為 ，請設定開啟此裝置相機， `true` 否則請將其 _關閉_。 </span><span class="sxs-lookup"><span data-stu-id="03023-204">If **Video default** in your worksheet is `true`, set **Turn on this device's camera** to on, otherwise leave it _off_.</span></span>
8. <span data-ttu-id="03023-205">如果 **工作表中** 已啟用視像，請選取在開啟此裝置相機下加入會議時允許 `true` **人員啟用**。 </span><span class="sxs-lookup"><span data-stu-id="03023-205">If **Video enabled** in your worksheet is `true`, select **Let people enable when joining a meeting** under **Turn on this device's camera**.</span></span> <span data-ttu-id="03023-206">如果開啟此裝置相機的設定為 開啟，則無法關閉 _此選項_。</span><span class="sxs-lookup"><span data-stu-id="03023-206">This option can't be turned off if **Turn on this device's camera** is set to _on_.</span></span>
9. <span data-ttu-id="03023-207">如果 **工作表中的 Whiteboard** 預設為 ，請設定開啟此裝置上的白板， `true` 否則請將其 _關閉_。  </span><span class="sxs-lookup"><span data-stu-id="03023-207">If **Whiteboard default** in your worksheet is `true`, set **Turn on whiteboarding on this device** to _on_, otherwise leave it _off_.</span></span>
10. <span data-ttu-id="03023-208">在 **信任的裝置帳戶下**，輸入工作表中列出 **之信任帳戶** 的每個 UPN。</span><span class="sxs-lookup"><span data-stu-id="03023-208">Under **Trusted device accounts**, type each UPN listed in **Trusted accounts** in your worksheet.</span></span> <span data-ttu-id="03023-209">使用逗號分隔多個 UPNs。</span><span class="sxs-lookup"><span data-stu-id="03023-209">Separate multiple UPNs with commas.</span></span>
11. <span data-ttu-id="03023-210">選取 **儲存並離開**。</span><span class="sxs-lookup"><span data-stu-id="03023-210">Select **Save and exit**.</span></span>

<span data-ttu-id="03023-211">選取儲存 **並離開之後**，裝置會重新開機，並準備好參與協調會議。</span><span class="sxs-lookup"><span data-stu-id="03023-211">After you select **Save and exit**, the device will restart and it'll be ready to participate in Coordinated Meetings.</span></span>

### <a name="use-the-teams-rooms-xml-configuration-file"></a><span data-ttu-id="03023-212">使用 Teams 會議室 XML 設定檔</span><span class="sxs-lookup"><span data-stu-id="03023-212">Use the Teams Rooms XML configuration file</span></span>

<span data-ttu-id="03023-213">您可以使用 Teams 會議室裝置中的 XML 設定檔來設定協調 `SkypeSettings.xml` 會議。</span><span class="sxs-lookup"><span data-stu-id="03023-213">Coordinated Meetings can be set up using the Teams Rooms device's `SkypeSettings.xml` XML configuration file.</span></span> <span data-ttu-id="03023-214">檔案 `SkypeSettings.xml` 不是靜態檔案。</span><span class="sxs-lookup"><span data-stu-id="03023-214">The `SkypeSettings.xml` file isn't a static file.</span></span> <span data-ttu-id="03023-215">當 Teams 會議室裝置啟動時，它會檢查 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 名為 `SkypeSettings.xml` 的檔案。</span><span class="sxs-lookup"><span data-stu-id="03023-215">When the Teams Rooms device start, it checks in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` for a file named `SkypeSettings.xml`.</span></span> <span data-ttu-id="03023-216">如果檔案存在，裝置會讀取並適用檔案中指定的組組。</span><span class="sxs-lookup"><span data-stu-id="03023-216">If the file exists, the device reads and applies the configuration specified in the file.</span></span> <span data-ttu-id="03023-217">完成安裝之後，檔案即會被刪除。</span><span class="sxs-lookup"><span data-stu-id="03023-217">After it's done applying the configuration, the file is deleted.</span></span> <span data-ttu-id="03023-218">有關檔案詳細資訊，請參閱 `SkypeSettings.xml` 使用 XML 設定檔 [管理主控台設定](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)。</span><span class="sxs-lookup"><span data-stu-id="03023-218">For more information about the `SkypeSettings.xml` file, see [Manage console settings with an XML configuration file](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file).</span></span>

<span data-ttu-id="03023-219">以下是設定檔中協調會議設定語法：</span><span class="sxs-lookup"><span data-stu-id="03023-219">The following is the syntax of the Coordinated Meetings settings in the configuration file:</span></span>

```xml
<CoordinatedMeetings enabled="true">
    <Settings>
        <Audio default="true" enabled="true"/>
        <Video default="true" enabled="true"/>
        <Whiteboard default="false" enabled="false"/>
    </Settings>
    <TrustedAccounts>hub@contoso.com</TrustedAccounts>
</CoordinatedMeetings>
```

<span data-ttu-id="03023-220">若要在裝置上設定協調會議，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="03023-220">To set up Coordinated Meetings on a device, do the following:</span></span>

1. <span data-ttu-id="03023-221">在文字檔編輯器中 ，例如 Visual Studio 程式碼或記事本，將上述 XML 貼到新檔案中。</span><span class="sxs-lookup"><span data-stu-id="03023-221">In a text file editor, such as Visual Studio Code or Notepad, paste the above XML into a new file.</span></span>

2. <span data-ttu-id="03023-222">將每個 XML 元素設定為試算表 `true` 中的對應 `false` 或值。</span><span class="sxs-lookup"><span data-stu-id="03023-222">Set each of the XML elements to the corresponding `true` or `false` value in your spreadsheet.</span></span> <span data-ttu-id="03023-223">例如，如果 **音訊預設值** 為 `true` ，則設定 `<Audio default="true">` 。</span><span class="sxs-lookup"><span data-stu-id="03023-223">For example, if **Audio default** is `true`, set `<Audio default="true">`.</span></span>

3. <span data-ttu-id="03023-224">請務必變更為 `TrustedAccounts` UPNs 清單。</span><span class="sxs-lookup"><span data-stu-id="03023-224">Be sure to change `TrustedAccounts` to your list of UPNs.</span></span>

4. <span data-ttu-id="03023-225">使用名稱儲存檔案 `SkypeSettings.xml` 。</span><span class="sxs-lookup"><span data-stu-id="03023-225">Save the file with the name `SkypeSettings.xml`.</span></span>

5. <span data-ttu-id="03023-226">將檔案放在 Teams 會議室裝置 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 的資料夾。</span><span class="sxs-lookup"><span data-stu-id="03023-226">Place the file in the Teams Rooms device's `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` folder.</span></span> <span data-ttu-id="03023-227">您可以用幾種方法執行此工作：</span><span class="sxs-lookup"><span data-stu-id="03023-227">You can do this a few ways:</span></span>

    - <span data-ttu-id="03023-228">**將檔案複製到您的 Teams 會議室裝置** 您必須啟用檔案共用並建立網路共用，才能將檔案複製到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="03023-228">**Copy the file to your Teams Rooms device** You'll need to enable file sharing and create a network share before you can copy files to your device.</span></span> <span data-ttu-id="03023-229">完成之後，您可以連接到網路共用，然後將檔案複製到裝置。</span><span class="sxs-lookup"><span data-stu-id="03023-229">After you do that, you can connect to network share and copy the file to the device.</span></span> <span data-ttu-id="03023-230">詳細資訊，請參閱 [Microsoft Teams 會議室的維護與作業](../rooms/rooms-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="03023-230">For more information, see [Microsoft Teams Rooms maintenance and operations](../rooms/rooms-operations.md).</span></span>
    - <span data-ttu-id="03023-231">**使用群組原則** 建立群組原則以將檔案複製到裝置。</span><span class="sxs-lookup"><span data-stu-id="03023-231">**Use a Group Policy** Create a group policy to copy the file to device.</span></span> <span data-ttu-id="03023-232">詳細資訊，請參閱 [群組原則概觀](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="03023-232">For more information, see [Group Policy Overview](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)).</span></span>
    - <span data-ttu-id="03023-233">**在 Teams 會議室裝置上下載檔案** 您可以使用系統管理模式登入裝置，然後將檔案從網路共用或 USB 磁碟機複製到裝置。</span><span class="sxs-lookup"><span data-stu-id="03023-233">**Download the file on the Teams Rooms device** You can log into the device using Admin mode and then copy the file to the device from a network share or USB drive.</span></span> <span data-ttu-id="03023-234">詳細資訊，請參閱 [切換到系統管理模式](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)。</span><span class="sxs-lookup"><span data-stu-id="03023-234">For more information, see [Switching to Admin mode](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>
    
6. <span data-ttu-id="03023-235">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="03023-235">Restart the device.</span></span> <span data-ttu-id="03023-236">您可以用幾種方法執行此工作：</span><span class="sxs-lookup"><span data-stu-id="03023-236">You can do this a couple ways:</span></span>

    - <span data-ttu-id="03023-237">**遠端 PowerShell** 您可以使用遠端 PowerShell 在裝置上執行關閉命令。</span><span class="sxs-lookup"><span data-stu-id="03023-237">**Remote PowerShell** You can run the Shutdown command on the device using Remote PowerShell.</span></span> <span data-ttu-id="03023-238">詳細資訊，請參閱使用 [PowerShell 進行遠端系統管理](../rooms/rooms-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="03023-238">For more information, see [Remote Management using PowerShell](../rooms/rooms-operations.md).</span></span>
    - <span data-ttu-id="03023-239">**執行重新開機電腦** 您可以在您的本地電腦上執行 `Restart-Computer` Cmdlet，並指定要重新開機之裝置的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="03023-239">**Run Restart-Computer** You can run the `Restart-Computer` cmdlet on your local computer and specify the computer name of the device you want to restart.</span></span> <span data-ttu-id="03023-240">詳細資訊，請參閱 [重新開機電腦](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="03023-240">For more information, see [Restart-Computer](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).</span></span>

## <a name="step-5-configure-surface-hub"></a><span data-ttu-id="03023-241">步驟 5：設定 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="03023-241">Step 5: Configure Surface Hub</span></span>

<span data-ttu-id="03023-242">您可以使用 Windows Configuration Designer 來建立一個設定套件，您可以使用該套件將協調會議設定套用至 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="03023-242">You can use Windows Configuration Designer to create a provisioning package that you can use to apply Coordinating Meetings settings to your Surface Hubs.</span></span> <span data-ttu-id="03023-243">您將上述所建立之 XML 檔案貼到 Windows Configuration Designer 中，以建立部署套件。</span><span class="sxs-lookup"><span data-stu-id="03023-243">You'll paste the XML file you created above into Windows Configuration Designer to create the provisioning package.</span></span>

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a><span data-ttu-id="03023-244">為 Surface Hub 建立協調會議 XML 設定檔</span><span class="sxs-lookup"><span data-stu-id="03023-244">Create Coordinated Meetings XML configuration file for Surface Hub</span></span>

<span data-ttu-id="03023-245">Windows 組組設計工具與 Microsoft Intune 都可用來將協調會議組適用于您的 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="03023-245">Both Windows Configuration Designer and Microsoft Intune are used to apply the Coordinated Meetings configuration to your Surface Hubs.</span></span> <span data-ttu-id="03023-246">此組組是使用 XML 定義。</span><span class="sxs-lookup"><span data-stu-id="03023-246">The configuration is defined using XML.</span></span> <span data-ttu-id="03023-247">在進一步進行之前，您需要建立要申請的 XML。</span><span class="sxs-lookup"><span data-stu-id="03023-247">Before you go further, you need to create the XML that will be applied.</span></span>

<span data-ttu-id="03023-248">以下是協調會議 XML 設定檔的語法。</span><span class="sxs-lookup"><span data-stu-id="03023-248">The following is the syntax of the Coordinated Meetings XML configuration file.</span></span>

```xml
<SurfaceHubSettings>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
    <CoordinatedMeetings enabled="true"> 
        <TrustedAccounts>room@contoso.com</TrustedAccounts>
        <Settings> 
            <Audio default="false" enabled="false" />
            <Video default="false" enabled="true" /> 
        </Settings> 
    </CoordinatedMeetings>
</SurfaceHubSettings>
```

<span data-ttu-id="03023-249">請執行下列操作，為 Windows 組組設計工具或 Microsoft Intune 準備 XML：</span><span class="sxs-lookup"><span data-stu-id="03023-249">Do the following to prepare the XML for Windows Configuration Designer or Microsoft Intune:</span></span>

1. <span data-ttu-id="03023-250">在文字檔編輯器中 ，例如 Visual Studio 程式碼或記事本，將上述 XML 貼到新檔案中。</span><span class="sxs-lookup"><span data-stu-id="03023-250">In a text file editor, such as Visual Studio Code or Notepad, paste the above XML into a new file.</span></span>

2. <span data-ttu-id="03023-251">將每個 XML 元素設定為試算表 `true` 中的對應 `false` 或值。</span><span class="sxs-lookup"><span data-stu-id="03023-251">Set each of the XML elements to the corresponding `true` or `false` value in your spreadsheet.</span></span> <span data-ttu-id="03023-252">例如，如果 **音訊預設值** 為 `true` ，則設定 `<Audio default="true">` 。</span><span class="sxs-lookup"><span data-stu-id="03023-252">For example, if **Audio default** is `true`, set `<Audio default="true">`.</span></span>

3. <span data-ttu-id="03023-253">請務必變更為 `TrustedAccounts` UPNs 清單。</span><span class="sxs-lookup"><span data-stu-id="03023-253">Be sure to change `TrustedAccounts` to your list of UPNs.</span></span>

4. <span data-ttu-id="03023-254">Windows Configuration Designer 要求 XML 位於單一行。</span><span class="sxs-lookup"><span data-stu-id="03023-254">Windows Configuration Designer requires that the XML be on a single line.</span></span> <span data-ttu-id="03023-255">移除每一行之間的所有分行符號，讓 XML 看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="03023-255">Remove all the line breaks between each line so that the XML looks like the following:</span></span>

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. <span data-ttu-id="03023-256">將檔案儲存在電腦上。</span><span class="sxs-lookup"><span data-stu-id="03023-256">Save the file on your computer.</span></span>

<span data-ttu-id="03023-257">建立 XML 組設定檔之後，請使用 Surface Hub 上的管理 [Microsoft Teams](surface-hub-manage-config.md) 設定中的步驟，將它適用于您的 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="03023-257">After you've created your XML configuration file, use the steps in [Manage Microsoft Teams settings on Surface Hub](surface-hub-manage-config.md) to apply it to your Surface Hubs.</span></span>