---
title: 遠端更新 Microsoft 團隊裝置
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
description: 使用 [團隊管理中心] 遠端更新 Microsoft 團隊手機和共同作業條
ms.openlocfilehash: 7e47c9394eddfa73b8b55279b68ae59ff7b6de3d
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944089"
---
# <a name="update-microsoft-teams-devices-remotely"></a><span data-ttu-id="282de-103">遠端更新 Microsoft 團隊裝置</span><span class="sxs-lookup"><span data-stu-id="282de-103">Update Microsoft Teams devices remotely</span></span>

<span data-ttu-id="282de-104">使用 Microsoft 團隊系統管理中心，您可以在遠端更新您的團隊裝置，例如，手機和共同作業條，您可以選擇 [裝置固件自動更新] 行為。</span><span class="sxs-lookup"><span data-stu-id="282de-104">Using the Microsoft Teams admin center, you can update your Teams devices, such as phones and collaboration bars, remotely, and you can choose device firmware automatic-update behavior.</span></span> <span data-ttu-id="282de-105">您可以使用 [團隊系統管理中心]，在您的裝置上更新下列專案：</span><span class="sxs-lookup"><span data-stu-id="282de-105">You can update the following on your devices using the Teams admin center:</span></span>

- <span data-ttu-id="282de-106">團隊 app 與團隊管理員代理</span><span class="sxs-lookup"><span data-stu-id="282de-106">Teams app and teams admin agent</span></span>
- <span data-ttu-id="282de-107">公司入口網站應用程式</span><span class="sxs-lookup"><span data-stu-id="282de-107">Company portal app</span></span>
- <span data-ttu-id="282de-108">OEM 代理應用程式</span><span class="sxs-lookup"><span data-stu-id="282de-108">OEM agent app</span></span>
- <span data-ttu-id="282de-109">裝置固件</span><span class="sxs-lookup"><span data-stu-id="282de-109">Device firmware</span></span>

<span data-ttu-id="282de-110">裝置固件更新可以自動套用，或排程未來的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="282de-110">Device firmware updates can either be applied automatically or scheduled for a future date and time.</span></span> <span data-ttu-id="282de-111">其他可用的裝置更新不會自動套用，但可以手動套用或排程未來的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="282de-111">Other available device updates aren't applied automatically, but can be applied manually or scheduled for a future date and time.</span></span>

> [!NOTE]
> <span data-ttu-id="282de-112">雖然可以排程裝置固件更新，但如果排程的日期和時間低於設定的最大30或90天的延遲，則在達到最大延遲時，就會套用固件更新。</span><span class="sxs-lookup"><span data-stu-id="282de-112">While device firmware updates can be scheduled, if the scheduled date and time falls after the configured maximum 30 or 90 day delay, the firmware update is applied when the maximum delay is reached.</span></span> <span data-ttu-id="282de-113">系統會忽略排程的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="282de-113">The scheduled date and time are ignored.</span></span>

## <a name="choose-automatic-device-firmware-update-behavior"></a><span data-ttu-id="282de-114">選擇自動裝置固件更新行為</span><span class="sxs-lookup"><span data-stu-id="282de-114">Choose automatic device firmware update behavior</span></span>

<span data-ttu-id="282de-115">裝置固件更新會自動套用。</span><span class="sxs-lookup"><span data-stu-id="282de-115">Device firmware updates are applied automatically.</span></span> <span data-ttu-id="282de-116">您可以決定是否要在發佈更新後立即套用更新，或在發行更新之後30或90天。</span><span class="sxs-lookup"><span data-stu-id="282de-116">You can decide whether to apply updates as soon as one is released, or 30 or 90 days after an update is released.</span></span> <span data-ttu-id="282de-117">根據預設，裝置固件更新會在30天發行後套用。</span><span class="sxs-lookup"><span data-stu-id="282de-117">By default, device firmware updates are applied 30 days one released.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="282de-118">您的小組裝置上未套用最新的固件更新發行。</span><span class="sxs-lookup"><span data-stu-id="282de-118">The latest firmware update release isn't applied on your Teams device.</span></span> <span data-ttu-id="282de-119">相反地，自動套用在您裝置上的更新會延遲一個版本。</span><span class="sxs-lookup"><span data-stu-id="282de-119">Instead, the update that's automatically applied on your device is delayed by one version.</span></span> <span data-ttu-id="282de-120">例如，假設您的裝置已套用版本「10」，且發行的版本為「11」。</span><span class="sxs-lookup"><span data-stu-id="282de-120">For example, assume your device has version "10" applied, and version "11" is released.</span></span> <span data-ttu-id="282de-121">版本 "11" 尚不適用。</span><span class="sxs-lookup"><span data-stu-id="282de-121">Version "11" won't be applied yet.</span></span> <span data-ttu-id="282de-122">在發行版本本 "12" 之後，您的裝置將只會更新為版本 "11"。</span><span class="sxs-lookup"><span data-stu-id="282de-122">Instead your device will only be updated to version "11" after version "12" is released.</span></span>

<span data-ttu-id="282de-123">若要選擇裝置的自動更新行為，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="282de-123">To choose the automatic update behavior for your devices, do the following:</span></span>

1. <span data-ttu-id="282de-124">透過造訪登入 Microsoft 團隊管理中心https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="282de-124">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="282de-125">流覽**裝置**  >  **手機**或共同作業**條**</span><span class="sxs-lookup"><span data-stu-id="282de-125">Navigate **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="282de-126">選取一或多個裝置，然後選取 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="282de-126">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="282de-127">在 [**固件自動更新**] 底下，選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="282de-127">Under **Firmware auto-update**, select one of the following:</span></span>
    - <span data-ttu-id="282de-128">只要**提供**第二-最新的裝置固件更新會在發行最新更新後儘快生效。</span><span class="sxs-lookup"><span data-stu-id="282de-128">**As soon as available** Second-newest device firmware update is applied as soon as possible after the latest update is released.</span></span>
    - <span data-ttu-id="282de-129">**推遲30天**第二-最新的裝置固件更新會在最近更新發行30天之後生效。</span><span class="sxs-lookup"><span data-stu-id="282de-129">**Defer 30 days** Second-newest device firmware update is applied 30 days after the latest update is released.</span></span>
    - <span data-ttu-id="282de-130">**推遲90天**第二-最新的裝置固件更新會在最近的更新發行之後90天生效。</span><span class="sxs-lookup"><span data-stu-id="282de-130">**Defer 90 days** Second-newest device firmware update is applied 90 days after the latest update is released.</span></span>
5. <span data-ttu-id="282de-131">選取 [**更新**]</span><span class="sxs-lookup"><span data-stu-id="282de-131">Select **Update**</span></span>

<span data-ttu-id="282de-132">如果出於任何原因，您需要復原裝置固件更新，您必須將裝置重設成出廠設定。</span><span class="sxs-lookup"><span data-stu-id="282de-132">If, for whatever reason, you need to revert a device firmware update, you need to reset your device to its factory settings.</span></span> <span data-ttu-id="282de-133">使用製造商提供的指示來重設您的裝置。</span><span class="sxs-lookup"><span data-stu-id="282de-133">Reset your device using the instructions from its manufacturer.</span></span>  

## <a name="manually-update-remote-devices"></a><span data-ttu-id="282de-134">手動更新遠端裝置</span><span class="sxs-lookup"><span data-stu-id="282de-134">Manually update remote devices</span></span>

<span data-ttu-id="282de-135">當您使用系統管理中心更新一或多個裝置時，您可以決定是否要立即更新裝置，或安排未來日期和時間的更新。</span><span class="sxs-lookup"><span data-stu-id="282de-135">When you update one or more devices using the admin center, you can decide whether to update the devices immediately or schedule an update for a future date and time.</span></span>

<span data-ttu-id="282de-136">若要手動更新遠端裝置，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="282de-136">To manually update remote devices, do the following:</span></span>

1. <span data-ttu-id="282de-137">透過造訪登入 Microsoft 團隊管理中心https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="282de-137">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="282de-138">流覽**裝置**  >  **手機**或共同作業**條**</span><span class="sxs-lookup"><span data-stu-id="282de-138">Navigate  **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="282de-139">選取一或多個裝置，然後選取 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="282de-139">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="282de-140">在 [**手動更新**] 底下，選取 [**排程**] （如果您想要針對未來的日期和時間排程更新）。</span><span class="sxs-lookup"><span data-stu-id="282de-140">Under **Manual updates**, select **Schedule** if you want to schedule the update for a future date and time.</span></span> <span data-ttu-id="282de-141">更新會套用至 [**時區**] 中所選取的時區中的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="282de-141">The updates are applied at the date and time in the timezone selected in **Timezone**.</span></span>

<span data-ttu-id="282de-142">您將會看到什麼，取決於您是否已選取一個或多個裝置。</span><span class="sxs-lookup"><span data-stu-id="282de-142">What you'll see depends on whether you have one, or multiple, devices selected.</span></span> <span data-ttu-id="282de-143">下圖顯示已選取多個裝置，而右側的影像顯示已選取單一裝置。</span><span class="sxs-lookup"><span data-stu-id="282de-143">The left image below shows multiple devices selected while the image on the right shows a single device selected.</span></span>

:::image type="content" source="../media/device-update-status.png" alt-text="[裝置更新狀態] 窗格中的單一和多個裝置視圖":::

<span data-ttu-id="282de-145">當您選取多個裝置時，可以選擇要將哪些更新類型套用至每個選取的裝置。</span><span class="sxs-lookup"><span data-stu-id="282de-145">When you select multiple devices, you can choose which update types to apply to each selected device.</span></span> <span data-ttu-id="282de-146">選取您要套用的更新類型，然後選取 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="282de-146">Select the update types you want to apply and select **Update**.</span></span>

<span data-ttu-id="282de-147">當您選取單一裝置時，會顯示可供裝置使用的更新。</span><span class="sxs-lookup"><span data-stu-id="282de-147">When you select a single device, updates that are available for the device are shown.</span></span> <span data-ttu-id="282de-148">如果有多個更新類型可供裝置使用，請選取要套用的每個更新類型。</span><span class="sxs-lookup"><span data-stu-id="282de-148">If multiple update types are available for the device, select each update type to apply.</span></span> <span data-ttu-id="282de-149">您可以在裝置上查看已套用的**目前版本**，以及將套用的**新版本**。</span><span class="sxs-lookup"><span data-stu-id="282de-149">You can view the **Current version** applied on the device and the **New version** that will be applied.</span></span> <span data-ttu-id="282de-150">選取您要套用的更新，然後選取 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="282de-150">Select the update(s) you want to apply and select **Update**.</span></span>

<span data-ttu-id="282de-151">選取 [**更新**] 後，如果您已安排更新，就會將更新套用至您所選的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="282de-151">After you select **Update**, updates are applied to your devices at the date and time you selected if you scheduled an update.</span></span> <span data-ttu-id="282de-152">如果您沒有選取未來的日期和時間，更新會在幾分鐘內套用至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="282de-152">If you didn't select a future date and time, updates are applied to your devices within a few minutes.</span></span>
