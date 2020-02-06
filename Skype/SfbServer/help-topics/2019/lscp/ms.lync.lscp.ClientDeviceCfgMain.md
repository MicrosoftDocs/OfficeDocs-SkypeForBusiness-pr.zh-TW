---
title: 裝置記錄組態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: 裝置更新 Web 服務可自動建立記錄檔，並記錄裝置的更新活動。 在組織的資料管理戰略中，您可能會想要針對記錄資料快取大小、記錄檔案大小，或在清除前的記錄檔案保留時間長度設定門限。 您可以根據組織的需求變更這些設定。 若您不希望裝置更新 Web 服務自動清除記錄檔，也可視需要手動加以清除。 您可以變更全域的記錄檔設定，或針對個別網站進行變更。
ms.openlocfilehash: 43fc784113a81038469099807770945ee2fbcc3b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794552"
---
# <a name="device-log-configuration"></a><span data-ttu-id="fd6c0-107">裝置記錄組態</span><span class="sxs-lookup"><span data-stu-id="fd6c0-107">Device Log Configuration</span></span>

<span data-ttu-id="fd6c0-108">裝置更新 Web 服務可自動建立記錄檔，並記錄裝置的更新活動。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="fd6c0-109">在組織的資料管理戰略中，您可能會想要針對記錄資料快取大小、記錄檔案大小，或在清除前的記錄檔案保留時間長度設定門限。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="fd6c0-110">您可以根據組織的需求變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="fd6c0-111">若您不希望裝置更新 Web 服務自動清除記錄檔，也可視需要手動加以清除。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="fd6c0-112">您可以變更全域的記錄檔設定，或針對個別網站進行變更。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="fd6c0-113">您也可以設定在一天的時間，讓裝置更新 Web 服務自動刪除超過您設定服務保留記錄檔案之天數的記錄檔案（預設為超過10天的記錄檔案）。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="fd6c0-114">此設定無法使用商務用 Skype Server [控制台] 進行修改。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="fd6c0-115">相反地，您必須使用商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="fd6c0-116">若要指定當天刪除過期記錄檔的時間，請使用**CsDeviceUpdateConfiguration** Cmdlet 搭配-LogCleanUpTimeOfDay 參數。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="fd6c0-117">如需詳細資訊，請參閱[新 CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="fd6c0-p104">清除檔案會從檔案系統將檔案永久移除。因此清除檔案後，您便無法復原檔案。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="fd6c0-120">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="fd6c0-120">Tasks you can perform</span></span>

<span data-ttu-id="fd6c0-121">您可以在「裝置記錄檔設定」\*\*\*\* 頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="fd6c0-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="fd6c0-122">針對全域或特定網站或集區，新增裝置記錄檔設定。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="fd6c0-123">修改現有裝置記錄檔設定的選項。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="fd6c0-124">UI 參考</span><span class="sxs-lookup"><span data-stu-id="fd6c0-124">UI Reference</span></span>

<span data-ttu-id="fd6c0-125">下列清單說明頁面上的功能表、命令、欄位及內容。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="fd6c0-126">**新增**您可以新增具有下列範圍的新裝置記錄配置：</span><span class="sxs-lookup"><span data-stu-id="fd6c0-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="fd6c0-127">全域</span><span class="sxs-lookup"><span data-stu-id="fd6c0-127">Global</span></span>

  - <span data-ttu-id="fd6c0-128">網站</span><span class="sxs-lookup"><span data-stu-id="fd6c0-128">Site</span></span>

- <span data-ttu-id="fd6c0-129">[**編輯**]您可以在清單中變更裝置記錄配置的選項。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="fd6c0-130">使用此選項，您可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fd6c0-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="fd6c0-131">**顯示詳細資料**這個選項會開啟一個對話方塊，您可以在其中變更裝置記錄配置的選項。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="fd6c0-132">**選取全部**此選項會選取清單中的所有裝置記錄配置。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="fd6c0-133">**刪除**這個選項會刪除所有選取的裝置記錄配置。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="fd6c0-134">**更新**您可以重新整理裝置記錄配置清單，以驗證所有裝置記錄配置選項的狀態。</span><span class="sxs-lookup"><span data-stu-id="fd6c0-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd6c0-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fd6c0-135">See also</span></span>

[<span data-ttu-id="fd6c0-136">Modify Settings for Log Files of Device Update Activity</span><span class="sxs-lookup"><span data-stu-id="fd6c0-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
