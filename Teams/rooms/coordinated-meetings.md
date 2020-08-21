---
title: 使用 Microsoft 團隊聊天室和 Surface Hub 來設定協同會議
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
description: 在一部裝置或其他人加入會議時，設定團隊室裝置和 Surface Hub 加入會議。
ms.openlocfilehash: cfd8bd423d8f7765a973d55e42d64773a06bba32
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803935"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a><span data-ttu-id="936b6-103">使用 Microsoft 團隊聊天室和 Surface Hub 來設定協同會議</span><span class="sxs-lookup"><span data-stu-id="936b6-103">Set up Coordinated Meetings with Microsoft Teams Rooms and Surface Hub</span></span>

<span data-ttu-id="936b6-104">如果您在會議室中有一個或多個 Microsoft 團隊聊天室裝置或 Surface Hub，您可以設定協同會議。</span><span class="sxs-lookup"><span data-stu-id="936b6-104">If you have one or more Microsoft Teams Rooms devices or Surface Hubs in a meeting room, you can set up Coordinated Meetings.</span></span> <span data-ttu-id="936b6-105">[協調式會議] 可讓您設定小組室裝置和 Surface Hub，這樣當您在一部裝置上加入會議時，會議室中的其他裝置也會加入相同的會議。</span><span class="sxs-lookup"><span data-stu-id="936b6-105">Coordinated Meetings lets you set up your Teams Rooms devices and Surface Hubs so that when you join a meeting on one device, the other devices in the room are also joined to the same meeting.</span></span> <span data-ttu-id="936b6-106">您可以設定相機、喇叭和麥克風，讓參與者能在其他人停用時啟用最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="936b6-106">You can configure your cameras, speakers, and microphones so that the ones that give participants the best experience are enabled while others are disabled.</span></span> <span data-ttu-id="936b6-107">如此一來，就能避免令人可怕的回音與意見反應，在新增多個裝置到會議時，可能會遇到</span><span class="sxs-lookup"><span data-stu-id="936b6-107">This avoids the dreaded echo and feedback noise participants can experience when adding multiple devices to a meeting.</span></span>

<span data-ttu-id="936b6-108">若要設定協同會議，您必須確認您的小組室裝置和 Surface Hub 已正確設定為參與會議。</span><span class="sxs-lookup"><span data-stu-id="936b6-108">To set up Coordinated Meetings, you need to make sure your Teams Rooms devices and Surface Hubs are already correctly configured to participate in meetings.</span></span> <span data-ttu-id="936b6-109">最重要的是，每個裝置都需要有自己的 Exchange 會議室信箱。</span><span class="sxs-lookup"><span data-stu-id="936b6-109">Most importantly, each device needs to have its own Exchange room mailbox.</span></span> <span data-ttu-id="936b6-110">如需如何設定的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="936b6-110">For information on how to set them up, see the following articles:</span></span>

- [<span data-ttu-id="936b6-111">部署 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="936b6-111">Deploy Microsoft Teams Rooms</span></span>](../rooms/rooms-deploy.md)
- [<span data-ttu-id="936b6-112">建立 Surface Hub 2 的裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="936b6-112">Create Surface Hub 2S device account</span></span>](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

<span data-ttu-id="936b6-113">確認您的小組機房裝置和 Surface Hub 可以自動接受會議並成功加入會議之後，您就可以設定協同會議。</span><span class="sxs-lookup"><span data-stu-id="936b6-113">After you've confirmed that your Teams Rooms devices and Surface Hubs can automatically accept meetings and join them successfully, you can set up Coordinated Meetings.</span></span>

<span data-ttu-id="936b6-114">必須針對每個會議室單獨完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="936b6-114">The following steps should be completed for each meeting room separately.</span></span> <span data-ttu-id="936b6-115">一個會議室中的裝置不應設定為與其他會議室中的裝置進行協調的會議。</span><span class="sxs-lookup"><span data-stu-id="936b6-115">Devices in one meeting room shouldn't be set up for Coordinated Meetings with devices in other meeting rooms.</span></span>

## <a name="step-1-plan-your-coordinated-meeting-experience"></a><span data-ttu-id="936b6-116">步驟1：規劃您的協同會議體驗</span><span class="sxs-lookup"><span data-stu-id="936b6-116">Step 1: Plan your Coordinated Meeting experience</span></span>

<span data-ttu-id="936b6-117">變更任何設定前，您必須決定哪些裝置將會在每個會議室中執行哪些動作。</span><span class="sxs-lookup"><span data-stu-id="936b6-117">Before you make any configuration changes, you need to decide which devices will do what in each meeting room.</span></span> <span data-ttu-id="936b6-118">亦即，對於指定的會議室，您必須決定要使用 [作用中麥克風]、[相機] 和 [白板] 的裝置。</span><span class="sxs-lookup"><span data-stu-id="936b6-118">That is, for a given meeting room, you need to decide which device will have the active microphone, camera, and whiteboard.</span></span> <span data-ttu-id="936b6-119">您設定裝置的方式取決於您的特定環境，以下是開始使用的一些一般建議：</span><span class="sxs-lookup"><span data-stu-id="936b6-119">How you configure your devices depends on your specific environment, but here are some general recommendations to start with:</span></span>

- <span data-ttu-id="936b6-120">**麥克風** 團隊聊天室裝置</span><span class="sxs-lookup"><span data-stu-id="936b6-120">**Microphone** Teams Rooms device</span></span>
- <span data-ttu-id="936b6-121">**相機** 團隊會議室裝置預設會 () 和 Surface Hub (預設為關閉，但允許) 參與者開啟</span><span class="sxs-lookup"><span data-stu-id="936b6-121">**Camera** Teams Rooms device (on by default) and Surface Hub (off by default, but allowed to be turned on by participants)</span></span>
- <span data-ttu-id="936b6-122">**白板** Surface Hub</span><span class="sxs-lookup"><span data-stu-id="936b6-122">**Whiteboard** Surface Hub</span></span>

> [!IMPORTANT]
> <span data-ttu-id="936b6-123">請確定您只在一個裝置上啟用麥克風。</span><span class="sxs-lookup"><span data-stu-id="936b6-123">Make sure you enable the microphone only on one device.</span></span> <span data-ttu-id="936b6-124">如果您在多個裝置上啟用，您會遇到音訊回音和意見反應。</span><span class="sxs-lookup"><span data-stu-id="936b6-124">If you enable it on more than one device, you'll experience audio echo and feedback.</span></span>

## <a name="step-2-get-your-devices-upns"></a><span data-ttu-id="936b6-125">步驟2：取得您的裝置 Upn</span><span class="sxs-lookup"><span data-stu-id="936b6-125">Step 2: Get your devices' UPNs</span></span>

<span data-ttu-id="936b6-126">當您在會議室中設定共同會議體驗時，您必須將小組室裝置和 Surface Hub 告知在該房間中要與之共同合作的裝置。</span><span class="sxs-lookup"><span data-stu-id="936b6-126">When you set up a Coordinated Meeting experience in a meeting room, you need to tell the Teams Rooms devices and Surface Hubs in that room which devices to coordinate with.</span></span> <span data-ttu-id="936b6-127">如此一來，您可以將使用者主體名稱 (UPN) 與其設定共同合作的裝置。</span><span class="sxs-lookup"><span data-stu-id="936b6-127">This is done by adding the user principal name (UPN) of the devices it should coordinate with to its configuration.</span></span> <span data-ttu-id="936b6-128">如果您不知道您想要為其設定協同會議的每個裝置的 Upn，您可以使用 Microsoft 365 系統管理中心來找到它們。</span><span class="sxs-lookup"><span data-stu-id="936b6-128">If you don't know the UPNs for each of the devices you want to set up for Coordinated Meetings, you can find them using the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="936b6-129">您必須獲指派系統管理員角色，才能存取 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="936b6-129">You need to be assigned an admin role to access the Microsoft 365 admin center.</span></span> <span data-ttu-id="936b6-130">如需詳細資訊，請參閱 [關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="936b6-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="936b6-131">若要取得團隊聊天室裝置和 Surface Hub 的 Upn，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="936b6-131">To get the UPNs of your Teams Rooms devices and Surface Hubs, do the following:</span></span>

1. <span data-ttu-id="936b6-132">透過造訪登入 Microsoft 365 系統管理中心 https://admin.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="936b6-132">Sign in to the Microsoft 365 admin center by visiting https://admin.microsoft.com.</span></span>
2. <span data-ttu-id="936b6-133">移至 [**使用者**作用  >  中的**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="936b6-133">Go to **Users** > **Active users**.</span></span>
3. <span data-ttu-id="936b6-134">在 [ **顯示名稱** ] 欄中尋找您團隊聊天室裝置或 Surface Hub 的名稱 (如果您有許多使用者) ，您就可以使用 [ **搜尋** ] 方塊。</span><span class="sxs-lookup"><span data-stu-id="936b6-134">Find the name of your Teams Rooms device or Surface Hub in the **Display name** column (you can use the **Search** box if you have many users).</span></span>
4. <span data-ttu-id="936b6-135">在 [使用者 **名稱** ] 欄中尋找 UPN， (它看起來像是 alias@contoso.com 或 alias@contoso.onmicrosoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="936b6-135">Find the UPN in the **Username** column (it'll look something like alias@contoso.com or alias@contoso.onmicrosoft.com).</span></span>
5. <span data-ttu-id="936b6-136">針對將參與協同會議的每個裝置，重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="936b6-136">Repeat this for each device that will participate in Coordinated Meetings.</span></span>

## <a name="step-3-create-a-deployment-worksheet"></a><span data-ttu-id="936b6-137">步驟3：建立部署工作表</span><span class="sxs-lookup"><span data-stu-id="936b6-137">Step 3: Create a deployment worksheet</span></span>

<span data-ttu-id="936b6-138">在您規劃了您的協調會議體驗並收集您的裝置 Upn 清單後，最好先建立部署工作表。</span><span class="sxs-lookup"><span data-stu-id="936b6-138">After you've planned your Coordinated Meeting experience and gathered a list of your devices' UPNs, it's a good idea to create a deployment worksheet.</span></span> <span data-ttu-id="936b6-139">部署工作表可協助您視覺化您想要在所有裝置上設定的設定，讓您驗證選項並檢查錯誤。</span><span class="sxs-lookup"><span data-stu-id="936b6-139">A deployment worksheet will help you visualize the configuration you want to set across all of your devices, allowing you to validate your choices and check for errors.</span></span>

<span data-ttu-id="936b6-140">在試算表應用程式中，在第一欄中新增下列各列：</span><span class="sxs-lookup"><span data-stu-id="936b6-140">In a spreadsheet app, add rows for the following in the first column:</span></span>

| <span data-ttu-id="936b6-141">設定</span><span class="sxs-lookup"><span data-stu-id="936b6-141">Setting</span></span>                | <span data-ttu-id="936b6-142">描述</span><span class="sxs-lookup"><span data-stu-id="936b6-142">Description</span></span>      |
|------------------------|-----------------|
| <span data-ttu-id="936b6-143">**音訊預設值**</span><span class="sxs-lookup"><span data-stu-id="936b6-143">**Audio default**</span></span>      | <span data-ttu-id="936b6-144">決定會議開始時麥克風起作用的裝置。</span><span class="sxs-lookup"><span data-stu-id="936b6-144">Determines on which device the microphone will be active when a meeting starts.</span></span> <span data-ttu-id="936b6-145">只有一個裝置 (通常是團隊會議室裝置) 可以將此欄位設定為， `true` 而其他裝置必須將此欄位設定為， `false` 以避免音訊回顯和意見反應。</span><span class="sxs-lookup"><span data-stu-id="936b6-145">Only one device (typically a Teams Rooms device) can have this field set to `true` while the rest of the devices must have this field set to `false` to avoid audio echo and feedback.</span></span>          |
| <span data-ttu-id="936b6-146">**已啟用音訊**</span><span class="sxs-lookup"><span data-stu-id="936b6-146">**Audio enabled**</span></span>      | <span data-ttu-id="936b6-147">決定會議中的參與者是否可以開啟或關閉麥克風。</span><span class="sxs-lookup"><span data-stu-id="936b6-147">Determines whether participants in a meeting can toggle the microphone on or off.</span></span> <span data-ttu-id="936b6-148">在其上設定 **音訊預設值** 的裝置， `false` 應該將此設定設定為， `false` 讓參與者不會不小心開啟麥克風並導致音訊回音或意見反應。</span><span class="sxs-lookup"><span data-stu-id="936b6-148">Devices on which **Audio default** is set to `false` should have this setting set to `false` so that participants can't accidentally turn on a microphone and cause audio echo or feedback.</span></span><p><span data-ttu-id="936b6-149">如果 [ **音訊預設值** ] 設定為 `true` ，則會忽略此設定，且參與者可以將麥克風設為靜音或取消靜音。</span><span class="sxs-lookup"><span data-stu-id="936b6-149">If **Audio default** is set to `true`, this setting is ignored and participants can mute or unmute the microphone.</span></span>          |
| <span data-ttu-id="936b6-150">**影片預設值**</span><span class="sxs-lookup"><span data-stu-id="936b6-150">**Video default**</span></span>      | <span data-ttu-id="936b6-151">決定會議開始時，相機在哪一個裝置上起作用。</span><span class="sxs-lookup"><span data-stu-id="936b6-151">Determines on which device the camera will be active when a meeting starts.</span></span> <span data-ttu-id="936b6-152">為了獲得最佳體驗，我們建議您只有在 `true` 所有其他裝置都設定為時，才會將小組聊天室裝置設定為 `false` 。</span><span class="sxs-lookup"><span data-stu-id="936b6-152">For the best experience, we recommend that only the Teams Rooms device be set to `true` while all other devices are set to `false`.</span></span>          |
| <span data-ttu-id="936b6-153">**已啟用影片**</span><span class="sxs-lookup"><span data-stu-id="936b6-153">**Video enabled**</span></span>      | <span data-ttu-id="936b6-154">決定會議中的參與者是否可以開啟或關閉相機。</span><span class="sxs-lookup"><span data-stu-id="936b6-154">Determines whether participants in a meeting can toggle the camera on or off.</span></span> <span data-ttu-id="936b6-155">您可以 `true` 在活動參與者中的任何其他裝置上將此設定為 [共用]， (例如參與者使用 Surface Hub 白板) 。</span><span class="sxs-lookup"><span data-stu-id="936b6-155">You can set this to `true` on any other devices in the event participants want to share different video perspectives (such as if a participant is using the Surface Hub whiteboard).</span></span> <span data-ttu-id="936b6-156">如果您不希望參與者在裝置上開啟或關閉相機，請將此選項設定為 `false` 。</span><span class="sxs-lookup"><span data-stu-id="936b6-156">If you don't want participants to turn a camera on or off on a device, set this to `false`.</span></span><p> <span data-ttu-id="936b6-157">如果 [ **影片預設值** ] 設定為 `true` ，則會忽略此設定，且參與者可以開啟或關閉相機。</span><span class="sxs-lookup"><span data-stu-id="936b6-157">If **Video default** is set to `true`, this setting is ignored and participants can turn the camera on or off.</span></span>         |
| <span data-ttu-id="936b6-158">**白板預設值**</span><span class="sxs-lookup"><span data-stu-id="936b6-158">**Whiteboard default**</span></span> | <span data-ttu-id="936b6-159">判斷小組聊天室裝置是否會顯示由其中一個會議參與者共用的白板。</span><span class="sxs-lookup"><span data-stu-id="936b6-159">Determines whether the Teams Rooms device will display a whiteboard shared by one of the meeting participants.</span></span> <span data-ttu-id="936b6-160">我們建議您將它設定為 `false` 如果您有 Surface Hub，且您沒有它 `true` 。</span><span class="sxs-lookup"><span data-stu-id="936b6-160">We recommend that you set this to `false` if you have a Surface Hub and `true` if you don't have one.</span></span> <span data-ttu-id="936b6-161">此設定不會影響 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="936b6-161">This setting has no effect on Surface Hubs.</span></span> <span data-ttu-id="936b6-162">Surface Hub 將永遠顯示由會議參與者共用的白板。</span><span class="sxs-lookup"><span data-stu-id="936b6-162">Surface Hubs will always display a whiteboard shared by meeting participants.</span></span>         |
| <span data-ttu-id="936b6-163">**已啟用白板**</span><span class="sxs-lookup"><span data-stu-id="936b6-163">**Whiteboard enabled**</span></span> | <span data-ttu-id="936b6-164">決定會議中的參與者是否可以開啟或關閉白板。</span><span class="sxs-lookup"><span data-stu-id="936b6-164">Determines whether participants in a meeting can toggle the whiteboard on or off.</span></span> <span data-ttu-id="936b6-165">如果您不希望參與者在裝置上開啟或關閉白板，請將此選項設定為 `false` 。</span><span class="sxs-lookup"><span data-stu-id="936b6-165">If you don't want participants to turn the whiteboard on or off on a device, set this to `false`.</span></span> <p><span data-ttu-id="936b6-166">如果 [ **白板預設** 設定] 是 [設為] `true` ，則會忽略此設定，且參與者可以開啟或關閉白板。</span><span class="sxs-lookup"><span data-stu-id="936b6-166">If **Whiteboard default** is set to `true`, this setting is ignored and participants can turn the whiteboard on or off.</span></span>
| <span data-ttu-id="936b6-167">**信任帳戶**</span><span class="sxs-lookup"><span data-stu-id="936b6-167">**Trusted accounts**</span></span>   | <span data-ttu-id="936b6-168">這是一個以逗號分隔的 Upn 清單，其中包含裝置應接受會議加入要求的每個小組房間裝置或 Surface Hub，或應傳送給哪個會議連接要求。</span><span class="sxs-lookup"><span data-stu-id="936b6-168">This is a comma-separated list of UPNs for each Teams Room device or Surface Hub that the device should accept meeting join requests from, or to which meeting join requests should be sent.</span></span> |

<span data-ttu-id="936b6-169">在後續的欄中，新增每個小組房間裝置和 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="936b6-169">In subsequent columns, add each of your Teams Rooms devices and Surface Hubs.</span></span> <span data-ttu-id="936b6-170">在每一欄中，填入與您想要的會議室相符的值。</span><span class="sxs-lookup"><span data-stu-id="936b6-170">In each column, fill out the values that correspond to the experience you want for the meeting room.</span></span> <span data-ttu-id="936b6-171">以下是一個團隊聊天室裝置和一個 Surface Hub 的範例：</span><span class="sxs-lookup"><span data-stu-id="936b6-171">Here's an example with one Teams Rooms device and one Surface Hub:</span></span>

- <span data-ttu-id="936b6-172">團隊裝置</span><span class="sxs-lookup"><span data-stu-id="936b6-172">Teams device</span></span>
  - <span data-ttu-id="936b6-173">**在會議開始時，** 音訊和影片都會開啟。</span><span class="sxs-lookup"><span data-stu-id="936b6-173">Audio and video are turned **on** when a meeting starts.</span></span> <span data-ttu-id="936b6-174">參與者 **可以** 開啟或關閉音訊與影片。</span><span class="sxs-lookup"><span data-stu-id="936b6-174">Participants **can** toggle audio and video on or off.</span></span>
  - <span data-ttu-id="936b6-175">顯示共用的白板功能已關閉。</span><span class="sxs-lookup"><span data-stu-id="936b6-175">Displaying a shared whiteboard is turned off.</span></span>
- <span data-ttu-id="936b6-176">Surface Hub</span><span class="sxs-lookup"><span data-stu-id="936b6-176">Surface Hub</span></span>
  - <span data-ttu-id="936b6-177">音訊會在會議開始時 **關閉** 。</span><span class="sxs-lookup"><span data-stu-id="936b6-177">Audio is turned **off** when a meeting starts.</span></span> <span data-ttu-id="936b6-178">參與者 **無法** 開啟或關閉音訊。</span><span class="sxs-lookup"><span data-stu-id="936b6-178">Participants **can't** toggle audio on or off.</span></span>
  - <span data-ttu-id="936b6-179">影片會在會議開始時 **關閉** 。</span><span class="sxs-lookup"><span data-stu-id="936b6-179">Video is turned **off** when a meeting starts.</span></span> <span data-ttu-id="936b6-180">參與者 **可以** 開啟或關閉影片。</span><span class="sxs-lookup"><span data-stu-id="936b6-180">Participants **can** toggle video on or off.</span></span>

| <span data-ttu-id="936b6-181">設定</span><span class="sxs-lookup"><span data-stu-id="936b6-181">Setting</span></span>                | <span data-ttu-id="936b6-182">團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="936b6-182">Teams Room</span></span>      | <span data-ttu-id="936b6-183">Surface Hub</span><span class="sxs-lookup"><span data-stu-id="936b6-183">Surface Hub</span></span>      |
|------------------------|-----------------|------------------|
| <span data-ttu-id="936b6-184">**音訊預設值**</span><span class="sxs-lookup"><span data-stu-id="936b6-184">**Audio default**</span></span>      | `true`          | `false`          |
| <span data-ttu-id="936b6-185">**已啟用音訊**</span><span class="sxs-lookup"><span data-stu-id="936b6-185">**Audio enabled**</span></span>      | `true`          | `false`          |
| <span data-ttu-id="936b6-186">**影片預設值**</span><span class="sxs-lookup"><span data-stu-id="936b6-186">**Video default**</span></span>      | `true`          | `false`          |
| <span data-ttu-id="936b6-187">**已啟用影片**</span><span class="sxs-lookup"><span data-stu-id="936b6-187">**Video enabled**</span></span>      | `true`          | `true`           |
| <span data-ttu-id="936b6-188">**白板預設值**</span><span class="sxs-lookup"><span data-stu-id="936b6-188">**Whiteboard default**</span></span> | `false`         | `false`          |
| <span data-ttu-id="936b6-189">**信任帳戶**</span><span class="sxs-lookup"><span data-stu-id="936b6-189">**Trusted accounts**</span></span>   | <span data-ttu-id="936b6-190">hub@contoso.com</span><span class="sxs-lookup"><span data-stu-id="936b6-190">hub@contoso.com</span></span> | <span data-ttu-id="936b6-191">room@contoso.com</span><span class="sxs-lookup"><span data-stu-id="936b6-191">room@contoso.com</span></span> |

## <a name="step-4-configure-teams-rooms-device"></a><span data-ttu-id="936b6-192">步驟4：設定團隊聊天室裝置</span><span class="sxs-lookup"><span data-stu-id="936b6-192">Step 4: Configure Teams Rooms device</span></span>

<span data-ttu-id="936b6-193">您可以使用裝置的觸控式螢幕在團隊聊天室裝置上設定共同作業，或者，如果您需要設定多個裝置，並想要從中央位置執行此操作，您可以使用 XML 設定檔。</span><span class="sxs-lookup"><span data-stu-id="936b6-193">You can either set up Coordinated Meetings on a Teams Rooms device using the device's touch screen or, if you need to set up many devices and want to do so from a central location, you can use an XML configuration file.</span></span>

<span data-ttu-id="936b6-194">使用您在上一個步驟中建立的工作表，協助您設定裝置。</span><span class="sxs-lookup"><span data-stu-id="936b6-194">Use the worksheet you created in the previous step to help you set up your devices.</span></span>

### <a name="use-the-teams-rooms-devices-touch-screen"></a><span data-ttu-id="936b6-195">使用團隊聊天室裝置的觸控式螢幕</span><span class="sxs-lookup"><span data-stu-id="936b6-195">Use the Teams Rooms device's touch screen</span></span>

<span data-ttu-id="936b6-196">若要在裝置上設定協同會議，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="936b6-196">To set up Coordinated Meetings on a device, do the following:</span></span>

1. <span data-ttu-id="936b6-197">選取 **.。。[其他**  >  **設定**]。</span><span class="sxs-lookup"><span data-stu-id="936b6-197">Select **... More** > **Settings**.</span></span>
2. <span data-ttu-id="936b6-198">輸入系統管理員密碼，然後選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="936b6-198">Enter the Administrator password and select **Yes**.</span></span>
3. <span data-ttu-id="936b6-199">選取 [ **協調的會議**]。</span><span class="sxs-lookup"><span data-stu-id="936b6-199">Select **Coordinated Meetings**.</span></span>
4. <span data-ttu-id="936b6-200">在 [ **選項**] 底下，將 [ **協調會議** ] 設定為 [ _開啟_]。</span><span class="sxs-lookup"><span data-stu-id="936b6-200">Under **Options**, set **Coordinated Meeting** to _on_.</span></span>
5. <span data-ttu-id="936b6-201">如果您工作表中的 [ **音訊預設值** ] 是 `true` ，請將 **此裝置的麥克風** 設定為 [開啟]，否則請將其 _關閉_。</span><span class="sxs-lookup"><span data-stu-id="936b6-201">If **Audio default** in your worksheet is `true`, set **Turn on this device's microphone** to on, otherwise leave it _off_.</span></span>
6. <span data-ttu-id="936b6-202">如果您的工作表中**啟用音訊** `true` ，請選取 [**開啟此裝置的麥克風**] 下的 [**讓人員在加入會議時啟用**]。</span><span class="sxs-lookup"><span data-stu-id="936b6-202">If **Audio enabled** in your worksheet is `true`, select **Let people enable when joining a meeting** under **Turn on this device's microphone**.</span></span> <span data-ttu-id="936b6-203">如果將 **此裝置的麥克風** 設為 [開啟]，則無法關閉此選項。</span><span class="sxs-lookup"><span data-stu-id="936b6-203">This option can't be turned off if **Turn on this device's microphone** is set to on.</span></span>
7. <span data-ttu-id="936b6-204">如果您工作表中的 [ **影片預設值** ] 是 `true` ，請將 **此裝置的相機** 設定為 [開啟]，否則請將其 _關閉_。</span><span class="sxs-lookup"><span data-stu-id="936b6-204">If **Video default** in your worksheet is `true`, set **Turn on this device's camera** to on, otherwise leave it _off_.</span></span>
8. <span data-ttu-id="936b6-205">如果您的工作表中啟用了 [**影片**] `true` ，請選取 [**開啟此裝置的相機**] 底下的 [**讓人員在加入會議時啟用**]。</span><span class="sxs-lookup"><span data-stu-id="936b6-205">If **Video enabled** in your worksheet is `true`, select **Let people enable when joining a meeting** under **Turn on this device's camera**.</span></span> <span data-ttu-id="936b6-206">如果將**此裝置的相機**設為 [開啟]，則無法關閉此_選項。_</span><span class="sxs-lookup"><span data-stu-id="936b6-206">This option can't be turned off if **Turn on this device's camera** is set to _on_.</span></span>
9. <span data-ttu-id="936b6-207">如果工作表中的 **白板預設值** 是 `true` ，請將 [ **開啟此裝置上的 whiteboarding** ] 設為 [開啟]，否則 _請_將其 _關閉_。</span><span class="sxs-lookup"><span data-stu-id="936b6-207">If **Whiteboard default** in your worksheet is `true`, set **Turn on whiteboarding on this device** to _on_, otherwise leave it _off_.</span></span>
10. <span data-ttu-id="936b6-208">在 [ **受信任的裝置帳戶**] 底下，于工作表的 [ **信任帳戶** ] 中，輸入每個 UPN。</span><span class="sxs-lookup"><span data-stu-id="936b6-208">Under **Trusted device accounts**, type each UPN listed in **Trusted accounts** in your worksheet.</span></span> <span data-ttu-id="936b6-209">使用逗號分隔多個 Upn。</span><span class="sxs-lookup"><span data-stu-id="936b6-209">Separate multiple UPNs with commas.</span></span>
11. <span data-ttu-id="936b6-210">選取 [ **儲存並**結束]。</span><span class="sxs-lookup"><span data-stu-id="936b6-210">Select **Save and exit**.</span></span>

<span data-ttu-id="936b6-211">在您選取 [ **儲存並**結束] 之後，裝置將會重新開機，並準備好參與協同會議。</span><span class="sxs-lookup"><span data-stu-id="936b6-211">After you select **Save and exit**, the device will restart and it'll be ready to participate in Coordinated Meetings.</span></span>

### <a name="use-the-teams-rooms-xml-configuration-file"></a><span data-ttu-id="936b6-212">使用團隊聊天室 XML 設定檔</span><span class="sxs-lookup"><span data-stu-id="936b6-212">Use the Teams Rooms XML configuration file</span></span>

<span data-ttu-id="936b6-213">您可以使用團隊聊天室裝置的 XML 設定檔來設定協同會議 `SkypeSettings.xml` 。</span><span class="sxs-lookup"><span data-stu-id="936b6-213">Coordinated Meetings can be set up using the Teams Rooms device's `SkypeSettings.xml` XML configuration file.</span></span> <span data-ttu-id="936b6-214">檔案 `SkypeSettings.xml` 不是靜態檔案。</span><span class="sxs-lookup"><span data-stu-id="936b6-214">The `SkypeSettings.xml` file isn't a static file.</span></span> <span data-ttu-id="936b6-215">小組聊天室裝置啟動時，會將檔案檢入至 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 名為的檔案 `SkypeSettings.xml` 。</span><span class="sxs-lookup"><span data-stu-id="936b6-215">When the Teams Rooms device start, it checks in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` for a file named `SkypeSettings.xml`.</span></span> <span data-ttu-id="936b6-216">如果檔案存在，裝置會讀取並套用檔案中指定的配置。</span><span class="sxs-lookup"><span data-stu-id="936b6-216">If the file exists, the device reads and applies the configuration specified in the file.</span></span> <span data-ttu-id="936b6-217">完成設定之後，就會刪除檔案。</span><span class="sxs-lookup"><span data-stu-id="936b6-217">After it's done applying the configuration, the file is deleted.</span></span> <span data-ttu-id="936b6-218">如需檔案的詳細資訊 `SkypeSettings.xml` ，請參閱 [使用 XML 設定檔管理主控台設定](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)。</span><span class="sxs-lookup"><span data-stu-id="936b6-218">For more information about the `SkypeSettings.xml` file, see [Manage console settings with an XML configuration file](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file).</span></span>

<span data-ttu-id="936b6-219">以下是設定檔中 [協調會議] 設定的語法：</span><span class="sxs-lookup"><span data-stu-id="936b6-219">The following is the syntax of the Coordinated Meetings settings in the configuration file:</span></span>

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

<span data-ttu-id="936b6-220">若要在裝置上設定協同會議，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="936b6-220">To set up Coordinated Meetings on a device, do the following:</span></span>

1. <span data-ttu-id="936b6-221">在文字檔編輯器（例如 Visual Studio 程式碼或記事本）中，將上述 XML 貼到新檔案中。</span><span class="sxs-lookup"><span data-stu-id="936b6-221">In a text file editor, such as Visual Studio Code or Notepad, paste the above XML into a new file.</span></span>

2. <span data-ttu-id="936b6-222">將每個 XML 元素設定為 `true` `false` 試算表中對應的 or 值。</span><span class="sxs-lookup"><span data-stu-id="936b6-222">Set each of the XML elements to the corresponding `true` or `false` value in your spreadsheet.</span></span> <span data-ttu-id="936b6-223">例如，如果 **音訊預設值** 為 `true` ，請設定 `<Audio default="true">` 。</span><span class="sxs-lookup"><span data-stu-id="936b6-223">For example, if **Audio default** is `true`, set `<Audio default="true">`.</span></span>

3. <span data-ttu-id="936b6-224">請務必變更 `TrustedAccounts` 為您的 upn 清單。</span><span class="sxs-lookup"><span data-stu-id="936b6-224">Be sure to change `TrustedAccounts` to your list of UPNs.</span></span>

4. <span data-ttu-id="936b6-225">以名稱儲存檔案 `SkypeSettings.xml` 。</span><span class="sxs-lookup"><span data-stu-id="936b6-225">Save the file with the name `SkypeSettings.xml`.</span></span>

5. <span data-ttu-id="936b6-226">將檔案放在團隊聊天室裝置的 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="936b6-226">Place the file in the Teams Rooms device's `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` folder.</span></span> <span data-ttu-id="936b6-227">您可以使用下列幾種方法來執行此動作：</span><span class="sxs-lookup"><span data-stu-id="936b6-227">You can do this a few ways:</span></span>

    - <span data-ttu-id="936b6-228">**將檔案複製到您的小組聊天室裝置** 您必須先啟用檔案共用並建立網路共用，才能將檔案複製到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="936b6-228">**Copy the file to your Teams Rooms device** You'll need to enable file sharing and create a network share before you can copy files to your device.</span></span> <span data-ttu-id="936b6-229">完成之後，您就可以連線到網路共用，並將檔案複製到裝置上。</span><span class="sxs-lookup"><span data-stu-id="936b6-229">After you do that, you can connect to network share and copy the file to the device.</span></span> <span data-ttu-id="936b6-230">如需詳細資訊，請參閱 [Microsoft 團隊會議室維護與作業](../rooms/rooms-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="936b6-230">For more information, see [Microsoft Teams Rooms maintenance and operations](../rooms/rooms-operations.md).</span></span>
    - <span data-ttu-id="936b6-231">**使用群組原則** 建立將檔案複製到裝置的群組原則。</span><span class="sxs-lookup"><span data-stu-id="936b6-231">**Use a Group Policy** Create a group policy to copy the file to device.</span></span> <span data-ttu-id="936b6-232">如需詳細資訊，請參閱 [群組原則概述](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="936b6-232">For more information, see [Group Policy Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)).</span></span>
    - <span data-ttu-id="936b6-233">**在團隊聊天室裝置上下載** 檔案您可以使用系統管理模式登入裝置，然後從網路共用或 USB 磁片磁碟機將檔案複製到裝置。</span><span class="sxs-lookup"><span data-stu-id="936b6-233">**Download the file on the Teams Rooms device** You can log into the device using Admin mode and then copy the file to the device from a network share or USB drive.</span></span> <span data-ttu-id="936b6-234">如需詳細資訊，請參閱 [切換到 [管理員模式]](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)。</span><span class="sxs-lookup"><span data-stu-id="936b6-234">For more information, see [Switching to Admin mode](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>
    
6. <span data-ttu-id="936b6-235">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="936b6-235">Restart the device.</span></span> <span data-ttu-id="936b6-236">您可以透過幾種方式來執行此動作：</span><span class="sxs-lookup"><span data-stu-id="936b6-236">You can do this a couple ways:</span></span>

    - <span data-ttu-id="936b6-237">**遠端 PowerShell** 您可以在使用遠端 PowerShell 的裝置上執行 [關閉] 命令。</span><span class="sxs-lookup"><span data-stu-id="936b6-237">**Remote PowerShell** You can run the Shutdown command on the device using Remote PowerShell.</span></span> <span data-ttu-id="936b6-238">如需詳細資訊，請參閱 [使用 PowerShell 進行遠端系統管理](../rooms/rooms-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="936b6-238">For more information, see [Remote Management using PowerShell](../rooms/rooms-operations.md).</span></span>
    - <span data-ttu-id="936b6-239">**執行重新開機-電腦** 您可以 `Restart-Computer` 在本機電腦上執行 Cmdlet，並指定您想要重新開機之裝置的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="936b6-239">**Run Restart-Computer** You can run the `Restart-Computer` cmdlet on your local computer and specify the computer name of the device you want to restart.</span></span> <span data-ttu-id="936b6-240">如需詳細資訊，請參閱 [重新開機電腦](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="936b6-240">For more information, see [Restart-Computer](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).</span></span>

## <a name="step-5-configure-surface-hub"></a><span data-ttu-id="936b6-241">步驟5：設定 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="936b6-241">Step 5: Configure Surface Hub</span></span>

<span data-ttu-id="936b6-242">您可以使用 Windows 配置設計工具來建立預配套件，您可以用來將 [協調會議] 設定套用到 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="936b6-242">You can use Windows Configuration Designer to create a provisioning package that you can use to apply Coordinating Meetings settings to your Surface Hubs.</span></span> <span data-ttu-id="936b6-243">您會將您在上面建立的 XML 檔案貼到 Windows 配置設計工具中，以建立預配套件。</span><span class="sxs-lookup"><span data-stu-id="936b6-243">You'll paste the XML file you created above into Windows Configuration Designer to create the provisioning package.</span></span>

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a><span data-ttu-id="936b6-244">建立 Surface Hub 的協調會議 XML 設定檔</span><span class="sxs-lookup"><span data-stu-id="936b6-244">Create Coordinated Meetings XML configuration file for Surface Hub</span></span>

<span data-ttu-id="936b6-245">Windows 配置設計工具和 Microsoft Intune 都是用來將 [協調會議] 設定套用到 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="936b6-245">Both Windows Configuration Designer and Microsoft Intune are used to apply the Coordinated Meetings configuration to your Surface Hubs.</span></span> <span data-ttu-id="936b6-246">此設定是使用 XML 定義的。</span><span class="sxs-lookup"><span data-stu-id="936b6-246">The configuration is defined using XML.</span></span> <span data-ttu-id="936b6-247">在您繼續進行之前，您必須先建立要套用的 XML。</span><span class="sxs-lookup"><span data-stu-id="936b6-247">Before you go further, you need to create the XML that will be applied.</span></span>

<span data-ttu-id="936b6-248">以下是協同會議 XML 設定檔的語法。</span><span class="sxs-lookup"><span data-stu-id="936b6-248">The following is the syntax of the Coordinated Meetings XML configuration file.</span></span>

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

<span data-ttu-id="936b6-249">請執行下列動作以準備 Windows 配置設計工具或 Microsoft Intune 版 XML：</span><span class="sxs-lookup"><span data-stu-id="936b6-249">Do the following to prepare the XML for Windows Configuration Designer or Microsoft Intune:</span></span>

1. <span data-ttu-id="936b6-250">在文字檔編輯器（例如 Visual Studio 程式碼或記事本）中，將上述 XML 貼到新檔案中。</span><span class="sxs-lookup"><span data-stu-id="936b6-250">In a text file editor, such as Visual Studio Code or Notepad, paste the above XML into a new file.</span></span>

2. <span data-ttu-id="936b6-251">將每個 XML 元素設定為 `true` `false` 試算表中對應的 or 值。</span><span class="sxs-lookup"><span data-stu-id="936b6-251">Set each of the XML elements to the corresponding `true` or `false` value in your spreadsheet.</span></span> <span data-ttu-id="936b6-252">例如，如果 **音訊預設值** 為 `true` ，請設定 `<Audio default="true">` 。</span><span class="sxs-lookup"><span data-stu-id="936b6-252">For example, if **Audio default** is `true`, set `<Audio default="true">`.</span></span>

3. <span data-ttu-id="936b6-253">請務必變更 `TrustedAccounts` 為您的 upn 清單。</span><span class="sxs-lookup"><span data-stu-id="936b6-253">Be sure to change `TrustedAccounts` to your list of UPNs.</span></span>

4. <span data-ttu-id="936b6-254">Windows 配置設計工具要求 XML 在單一行上。</span><span class="sxs-lookup"><span data-stu-id="936b6-254">Windows Configuration Designer requires that the XML be on a single line.</span></span> <span data-ttu-id="936b6-255">移除各行之間的所有分行符號，使 XML 看起來像以下這樣：</span><span class="sxs-lookup"><span data-stu-id="936b6-255">Remove all the line breaks between each line so that the XML looks like the following:</span></span>

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. <span data-ttu-id="936b6-256">將檔案儲存在您的電腦上。</span><span class="sxs-lookup"><span data-stu-id="936b6-256">Save the file on your computer.</span></span>

<span data-ttu-id="936b6-257">建立 XML 設定檔之後，請使用「 [管理 Surface Hub 上的 Microsoft 團隊設定](surface-hub-manage-config.md) 」中的步驟，將其套用至 surface hub。</span><span class="sxs-lookup"><span data-stu-id="936b6-257">After you've created your XML configuration file, use the steps in [Manage Microsoft Teams settings on Surface Hub](surface-hub-manage-config.md) to apply it to your Surface Hubs.</span></span>