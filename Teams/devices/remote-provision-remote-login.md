---
title: Teams Android 裝置遠端置備及登錄
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: prgholve
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何遠端提供和登錄 Teams Android 裝置
ms.openlocfilehash: 43a025c0cc68fb7f10015d69298f8dd75f9003e8
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410335"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a><span data-ttu-id="afc11-103">Teams Android 裝置遠端置備及登錄</span><span class="sxs-lookup"><span data-stu-id="afc11-103">Remote provisioning and sign in for Teams Android devices</span></span>

<span data-ttu-id="afc11-104">IT 系統管理員可以遠端撥備並登錄 Teams Android 裝置。</span><span class="sxs-lookup"><span data-stu-id="afc11-104">IT admins can remotely provision and sign in to a Teams Android device.</span></span> <span data-ttu-id="afc11-105">若要遠端置備裝置，系統管理員必須上傳所配置之裝置之 MAC ID，並建立驗證碼。</span><span class="sxs-lookup"><span data-stu-id="afc11-105">To provision a device remotely, the admin needs to upload the MAC IDs of the devices being provisioned and create a verification code.</span></span> <span data-ttu-id="afc11-106">整個程式可以從 Teams 系統管理中心遠端完成。</span><span class="sxs-lookup"><span data-stu-id="afc11-106">The entire process can be completed remotely from the Teams admin center.</span></span>

## <a name="review-the-supported-devices"></a><span data-ttu-id="afc11-107">檢查支援的裝置</span><span class="sxs-lookup"><span data-stu-id="afc11-107">Review the supported devices</span></span>

<span data-ttu-id="afc11-108">下列清單顯示 Android 裝置固件需求。</span><span class="sxs-lookup"><span data-stu-id="afc11-108">The following list shows the Android device firmware requirements.</span></span>

|<span data-ttu-id="afc11-109">裝置類別</span><span class="sxs-lookup"><span data-stu-id="afc11-109">Device category</span></span>|<span data-ttu-id="afc11-110">裝置模型</span><span class="sxs-lookup"><span data-stu-id="afc11-110">Device model</span></span>|<span data-ttu-id="afc11-111">固件版本</span><span class="sxs-lookup"><span data-stu-id="afc11-111">Firmware version</span></span>|
|-|-|-|
|<span data-ttu-id="afc11-112">Teams 電話</span><span class="sxs-lookup"><span data-stu-id="afc11-112">Teams phones</span></span>|<span data-ttu-id="afc11-113">Yealink T55/T56/T58</span><span class="sxs-lookup"><span data-stu-id="afc11-113">Yealink T55/T56/T58</span></span>|<span data-ttu-id="afc11-114">58.15.0.124</span><span class="sxs-lookup"><span data-stu-id="afc11-114">58.15.0.124</span></span>|
|<span data-ttu-id="afc11-115">Teams 電話</span><span class="sxs-lookup"><span data-stu-id="afc11-115">Teams phones</span></span>|<span data-ttu-id="afc11-116">Yealink VP59</span><span class="sxs-lookup"><span data-stu-id="afc11-116">Yealink VP59</span></span>|<span data-ttu-id="afc11-117">91.15.0.58</span><span class="sxs-lookup"><span data-stu-id="afc11-117">91.15.0.58</span></span>|
|<span data-ttu-id="afc11-118">Teams 電話</span><span class="sxs-lookup"><span data-stu-id="afc11-118">Teams phones</span></span>|<span data-ttu-id="afc11-119">Yealink CP960</span><span class="sxs-lookup"><span data-stu-id="afc11-119">Yealink CP960</span></span>|<span data-ttu-id="afc11-120">73.15.0.117</span><span class="sxs-lookup"><span data-stu-id="afc11-120">73.15.0.117</span></span>|
|<span data-ttu-id="afc11-121">Teams 電話</span><span class="sxs-lookup"><span data-stu-id="afc11-121">Teams phones</span></span>|<span data-ttu-id="afc11-122">Yealink MP56/MP54/MP58</span><span class="sxs-lookup"><span data-stu-id="afc11-122">Yealink MP56/MP54/MP58</span></span>|<span data-ttu-id="afc11-123">122.15.0.36</span><span class="sxs-lookup"><span data-stu-id="afc11-123">122.15.0.36</span></span>|
|<span data-ttu-id="afc11-124">Teams 電話</span><span class="sxs-lookup"><span data-stu-id="afc11-124">Teams phones</span></span>|<span data-ttu-id="afc11-125">Cresron UC-2</span><span class="sxs-lookup"><span data-stu-id="afc11-125">Crestron UC-2</span></span>|<span data-ttu-id="afc11-126">1.0.3.52</span><span class="sxs-lookup"><span data-stu-id="afc11-126">1.0.3.52</span></span>|

## <a name="add-a-device-mac-address"></a><span data-ttu-id="afc11-127">新增裝置 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="afc11-127">Add a device MAC address</span></span>

<span data-ttu-id="afc11-128">完成下列步驟以配置新裝置。</span><span class="sxs-lookup"><span data-stu-id="afc11-128">Complete the following steps to provision a new device.</span></span>

1. <span data-ttu-id="afc11-129">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="afc11-129">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="afc11-130">展開 **裝置**。</span><span class="sxs-lookup"><span data-stu-id="afc11-130">Expand **Devices**.</span></span>
3. <span data-ttu-id="afc11-131">從 **動作選項卡中選取** 置 **備新** 裝置。</span><span class="sxs-lookup"><span data-stu-id="afc11-131">Select **Provision new device** from the **Actions** tab.</span></span>

<span data-ttu-id="afc11-132">在安裝 **新裝置** 視窗中，您可以手動新增 MAC 位址或上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="afc11-132">In the **Provision new devices** window, you can either add the MAC address manually or upload a file.</span></span>

### <a name="manually-add-a-device-mac-address"></a><span data-ttu-id="afc11-133">手動新增裝置 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="afc11-133">Manually add a device MAC address</span></span>

1. <span data-ttu-id="afc11-134">從等待 **啟用的** 選項卡中，選取 **新增 MAC 識別碼**。</span><span class="sxs-lookup"><span data-stu-id="afc11-134">From the **Awaiting Activation** tab, select **Add MAC ID**.</span></span>

   ![手動新增裝置 mac 位址](../media/remote-provision-6.png)

1. <span data-ttu-id="afc11-136">輸入 MAC 識別碼。</span><span class="sxs-lookup"><span data-stu-id="afc11-136">Enter the MAC ID.</span></span>
1. <span data-ttu-id="afc11-137">輸入位置，協助技術人員識別安裝裝置的位置。</span><span class="sxs-lookup"><span data-stu-id="afc11-137">Enter a location, which helps technicians identify where to install the devices.</span></span>
1. <span data-ttu-id="afc11-138">完成 **時選取 Apply。**</span><span class="sxs-lookup"><span data-stu-id="afc11-138">Select **Apply** when finished.</span></span>

### <a name="upload-a-file-to-add-a-device-mac-address"></a><span data-ttu-id="afc11-139">上傳檔案以新增裝置 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="afc11-139">Upload a file to add a device MAC address</span></span>

1. <span data-ttu-id="afc11-140">從等待 **啟用的** 選項卡中，選取 **上傳 MAC ID。**</span><span class="sxs-lookup"><span data-stu-id="afc11-140">From the **Awaiting Activation** tab, select **Upload MAC IDs**.</span></span>
2. <span data-ttu-id="afc11-141">下載檔案範本。</span><span class="sxs-lookup"><span data-stu-id="afc11-141">Download the file template.</span></span>
3. <span data-ttu-id="afc11-142">輸入 MAC 識別碼和位置，然後儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="afc11-142">Enter the MAC ID and location, and then save the file.</span></span>
4. <span data-ttu-id="afc11-143">**選取檔案**， **然後選取** 上傳 。</span><span class="sxs-lookup"><span data-stu-id="afc11-143">**Select file**, and then select **Upload**.</span></span>

## <a name="generate-a-verification-code"></a><span data-ttu-id="afc11-144">產生驗證碼</span><span class="sxs-lookup"><span data-stu-id="afc11-144">Generate a verification code</span></span>

<span data-ttu-id="afc11-145">您需要裝置驗證碼。</span><span class="sxs-lookup"><span data-stu-id="afc11-145">You need a verification code for the devices.</span></span> <span data-ttu-id="afc11-146">驗證碼會大量產生或在裝置層級產生，且有效 24 小時。</span><span class="sxs-lookup"><span data-stu-id="afc11-146">The verification code is generated in bulk or at the device level and is valid for 24 hours.</span></span>

1. <span data-ttu-id="afc11-147">從等待 **啟用的** 選項卡中，選取現有的 MAC 識別碼。</span><span class="sxs-lookup"><span data-stu-id="afc11-147">From the **Awaiting Activation** tab, select an existing MAC ID.</span></span>
   <span data-ttu-id="afc11-148">MAC 位址會建立密碼，且會顯示在驗證 **碼欄中** 。</span><span class="sxs-lookup"><span data-stu-id="afc11-148">A password is created for the MAC address and is shown in the **Verification Code** column.</span></span>

2. <span data-ttu-id="afc11-149">提供 MAC ID 和驗證碼清單給現場技術人員。</span><span class="sxs-lookup"><span data-stu-id="afc11-149">Provide the list of MAC IDs and verification codes to the field technicians.</span></span> <span data-ttu-id="afc11-150">您可以直接在檔案中匯出詳細資料，並與執行實際安裝工作的技術人員共用檔案。</span><span class="sxs-lookup"><span data-stu-id="afc11-150">You can export the detail directly in a file and share the file with the technician who is doing the actual installation work.</span></span>

## <a name="provision-the-device"></a><span data-ttu-id="afc11-151">置備裝置</span><span class="sxs-lookup"><span data-stu-id="afc11-151">Provision the device</span></span>

<span data-ttu-id="afc11-152">當裝置已電源開啟並連接至網路時，技術人員會配置裝置。</span><span class="sxs-lookup"><span data-stu-id="afc11-152">When the device is powered on and connected to the network, the technician provisions the device.</span></span> <span data-ttu-id="afc11-153">這些步驟在 Teams 裝置上完成。</span><span class="sxs-lookup"><span data-stu-id="afc11-153">These steps are completed on the Teams device.</span></span>

1. <span data-ttu-id="afc11-154">技術人員會從設定 **中選取** 設定 **裝置**。</span><span class="sxs-lookup"><span data-stu-id="afc11-154">The technician selects **Provision device** from the **Settings**.</span></span>  

   ![從動作選項卡中置備新裝置選項](../media/provision-device1.png)
  
2. <span data-ttu-id="afc11-156">技術人員在提供的輸入欄位中輸入裝置專用驗證碼。</span><span class="sxs-lookup"><span data-stu-id="afc11-156">The technician enters the device-specific verification code in the provided input field.</span></span>

   ![提供新裝置驗證](../media/provision-device-verification1.png)

   <span data-ttu-id="afc11-158">成功配置裝置後，租使用者名稱會顯示在登錄頁面上。</span><span class="sxs-lookup"><span data-stu-id="afc11-158">Once the device is provisioned successfully, the tenant name appears on the sign-in page.</span></span>

   ![登錄頁面上的租使用者名稱](../media/provision-code.png)

## <a name="sign-in-remotely"></a><span data-ttu-id="afc11-160">遠端登入</span><span class="sxs-lookup"><span data-stu-id="afc11-160">Sign in remotely</span></span>

<span data-ttu-id="afc11-161">已置備的裝置會出現在等待 **登錄的選項卡** 中。選取個別裝置以啟動遠端登入程式。</span><span class="sxs-lookup"><span data-stu-id="afc11-161">The provisioned device appears in the **Awaiting sign in** tab. Start the remote sign-in process by selecting the individual device.</span></span>

1. <span data-ttu-id="afc11-162">從等待登錄的 **選項卡中選取** 裝置。</span><span class="sxs-lookup"><span data-stu-id="afc11-162">Select a device from the **Awaiting sign in** tab.</span></span>

   ![已準備要登錄之裝置清單的視窗。](../media/remote-device1.png)

2. <span data-ttu-id="afc11-164">請遵循使用者 **登錄中的指示，** 然後選取 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="afc11-164">Follow the instructions in **Sign in a user**, and then select **Close**.</span></span>

   ![個別裝置的使用者視窗](../media/sign-in-user.png)

## <a name="related-article"></a><span data-ttu-id="afc11-166">相關文章</span><span class="sxs-lookup"><span data-stu-id="afc11-166">Related article</span></span>

- [<span data-ttu-id="afc11-167">在 Teams 中管理裝置</span><span class="sxs-lookup"><span data-stu-id="afc11-167">Manage your devices in Teams</span></span>](device-management.md)
- [<span data-ttu-id="afc11-168">遠端更新 Teams 裝置</span><span class="sxs-lookup"><span data-stu-id="afc11-168">Update Teams devices remotely</span></span>](remote-update.md)
