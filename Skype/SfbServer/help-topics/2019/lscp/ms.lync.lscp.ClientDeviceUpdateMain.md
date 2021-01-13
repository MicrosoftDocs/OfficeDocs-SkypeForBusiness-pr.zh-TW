---
title: 裝置更新
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 會定期為商務用 Skype Phone Edition 發行一組新的裝置固件更新，您可以將其匯入伺服器並散佈給使用者。 您可以移至 Microsoft 網站上的 [說明與支援] 頁面，並搜尋 forPhone Edition，以取得最新的裝置更新規則集合。下載最新的更新套件，並將檔案解壓縮至要上傳更新的電腦資料夾。 解壓縮檔案後，接著可以使用 Import-CsDeviceUpdate Cmdlet 匯入解壓縮後之 .CAB 檔案 (其名稱為 UCUpdates.cab) 中的裝置更新規則。 如需詳細資訊，請參閱 Import-CsDeviceUpdate。
ms.openlocfilehash: cd8b983990ff3bc5843c252a153eafaa47cd9a1e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830283"
---
# <a name="device-update"></a><span data-ttu-id="ca181-106">裝置更新</span><span class="sxs-lookup"><span data-stu-id="ca181-106">Device Update</span></span>

<span data-ttu-id="ca181-107">Microsoft 會定期為商務用 Skype Phone Edition 發行一組新的裝置固件更新，您可以將其匯入伺服器並散佈給使用者。</span><span class="sxs-lookup"><span data-stu-id="ca181-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="ca181-108">前往 Microsoft 網站的「說明及支援」頁面並搜尋 "Phone Edition" 可取得最新的裝置更新規則組合。</span><span class="sxs-lookup"><span data-stu-id="ca181-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="ca181-109">下載最新的更新套件，將檔案解壓縮至要上載之更新所在的電腦資料夾內。</span><span class="sxs-lookup"><span data-stu-id="ca181-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="ca181-110">解壓縮檔案後，接著可以使用 **Import-CsDeviceUpdate** Cmdlet 匯入解壓縮後之 .CAB 檔案 (其名稱為 UCUpdates.cab) 中的裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="ca181-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="ca181-111">如需詳細資訊，請參閱 [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="ca181-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="ca181-112">在匯入裝置更新規則之後，您可以使用「 **裝置更新** 」頁面，為您組織的裝置查看及管理這些規則。</span><span class="sxs-lookup"><span data-stu-id="ca181-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="ca181-113">您可以測試韌體更新，假設更新成功之後，再接著讓組織中使用的所有相關裝置使用此更新。</span><span class="sxs-lookup"><span data-stu-id="ca181-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="ca181-114">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="ca181-114">Tasks you can perform</span></span>

<span data-ttu-id="ca181-115">您可在「裝置更新」頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="ca181-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="ca181-116">核准清單中的裝置更新。</span><span class="sxs-lookup"><span data-stu-id="ca181-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="ca181-117">取消或回復擱置的裝置更新。</span><span class="sxs-lookup"><span data-stu-id="ca181-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="ca181-118">從清單刪除裝置更新。</span><span class="sxs-lookup"><span data-stu-id="ca181-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="ca181-119">UI 參考</span><span class="sxs-lookup"><span data-stu-id="ca181-119">UI Reference</span></span>

<span data-ttu-id="ca181-120">下列清單說明頁面上的功能表、命令、欄位及內容。</span><span class="sxs-lookup"><span data-stu-id="ca181-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="ca181-121">**編輯** 您可以使用此選項執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ca181-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="ca181-122">**全選** 此選項會選取清單中的所有裝置更新。</span><span class="sxs-lookup"><span data-stu-id="ca181-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="ca181-123">**Delete** 此選項會刪除所有選取的裝置更新。</span><span class="sxs-lookup"><span data-stu-id="ca181-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="ca181-124">**動作** 您可以在清單中選取一或多個更新，並採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="ca181-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="ca181-125">**取消暫** 止的更新此選項可防止選取的更新部署至您組織的裝置。</span><span class="sxs-lookup"><span data-stu-id="ca181-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="ca181-126">**核准** 此選項允許將選取的更新部署至您組織的裝置。</span><span class="sxs-lookup"><span data-stu-id="ca181-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="ca181-127">**還原** 此選項允許將先前核准的更新部署至您組織的裝置</span><span class="sxs-lookup"><span data-stu-id="ca181-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="ca181-128">**Refresh** 您可以重新整理清單，以確認所有裝置更新的狀態。</span><span class="sxs-lookup"><span data-stu-id="ca181-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="ca181-129">如需裝置更新 Web 服務的詳細資訊，請參閱規劃文件中的＜[View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)＞。</span><span class="sxs-lookup"><span data-stu-id="ca181-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="ca181-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ca181-130">See also</span></span>

[<span data-ttu-id="ca181-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="ca181-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
