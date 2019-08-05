---
title: 裝置更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 會定期針對商務用 Skype Phone Edition 發行一組新的裝置固件更新, 您可以匯入到伺服器並散佈給使用者。 您可以移至 Microsoft 網站上的 [說明及支援] 頁面, 並搜尋 forPhone Edition, 以取得最新的裝置更新規則組。下載最新的更新套件, 並將檔案解壓縮至電腦上要上傳更新的資料夾。 解壓縮檔案後，接著可以使用 Import-CsDeviceUpdate Cmdlet 匯入解壓縮後之 .CAB 檔案 (其名稱為 UCUpdates.cab) 中的裝置更新規則。 如需詳細資訊, 請參閱匯入-CsDeviceUpdate。
ms.openlocfilehash: 19b0253dece8b010fc4de4fe3907cf8cff2a5bf9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193229"
---
# <a name="device-update"></a><span data-ttu-id="9e607-106">裝置更新</span><span class="sxs-lookup"><span data-stu-id="9e607-106">Device Update</span></span>

<span data-ttu-id="9e607-107">Microsoft 會定期針對商務用 Skype Phone Edition 發行一組新的裝置固件更新, 您可以匯入到伺服器並散佈給使用者。</span><span class="sxs-lookup"><span data-stu-id="9e607-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="9e607-108">前往 Microsoft 網站的「說明及支援」頁面並搜尋 "Phone Edition" (電話版) 可取得最新的裝置更新規則組合。</span><span class="sxs-lookup"><span data-stu-id="9e607-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="9e607-109">下載最新的更新套件，將檔案解壓縮至要上載之更新所在的電腦資料夾內。</span><span class="sxs-lookup"><span data-stu-id="9e607-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="9e607-110">解壓縮檔案後，接著可以使用 **Import-CsDeviceUpdate** Cmdlet 匯入解壓縮後之 .CAB 檔案 (其名稱為 UCUpdates.cab) 中的裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="9e607-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="9e607-111">如需詳細資訊, 請參閱匯[入-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="9e607-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="9e607-112">在已匯入裝置更新規則之後, 您可以使用 [**裝置更新**] 頁面來查看及管理貴組織裝置的這些規則。</span><span class="sxs-lookup"><span data-stu-id="9e607-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="9e607-113">您可以測試韌體更新，假設測試成功，再接著讓組織中使用的所有相關裝置使用此更新。</span><span class="sxs-lookup"><span data-stu-id="9e607-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="9e607-114">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="9e607-114">Tasks you can perform</span></span>

<span data-ttu-id="9e607-115">您可在「裝置更新」\*\*\*\* 頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="9e607-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="9e607-116">核准清單中的裝置更新。</span><span class="sxs-lookup"><span data-stu-id="9e607-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="9e607-117">取消或回復擱置的裝置更新。</span><span class="sxs-lookup"><span data-stu-id="9e607-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="9e607-118">從清單刪除裝置更新。</span><span class="sxs-lookup"><span data-stu-id="9e607-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="9e607-119">UI 參考</span><span class="sxs-lookup"><span data-stu-id="9e607-119">UI Reference</span></span>

<span data-ttu-id="9e607-120">下列清單說明頁面上的功能表、命令、欄位及內容。</span><span class="sxs-lookup"><span data-stu-id="9e607-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="9e607-121">[**編輯**]您可以使用這個選項來執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="9e607-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="9e607-122">**選取全部**此選項會選取清單中的所有裝置更新。</span><span class="sxs-lookup"><span data-stu-id="9e607-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="9e607-123">**刪除**這個選項會刪除所有選取的裝置更新。</span><span class="sxs-lookup"><span data-stu-id="9e607-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="9e607-124">**動作**您可以在清單中選取一或多個更新, 並執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="9e607-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="9e607-125">**解除擱置**中的更新這個選項可防止將選取的更新部署到貴組織的裝置上。</span><span class="sxs-lookup"><span data-stu-id="9e607-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="9e607-126">**核准**這個選項可讓選取的更新部署到貴組織的裝置上。</span><span class="sxs-lookup"><span data-stu-id="9e607-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="9e607-127">**還原**這個選項可讓先前核准的更新部署到貴組織的裝置上</span><span class="sxs-lookup"><span data-stu-id="9e607-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="9e607-128">**更新**您可以重新整理清單, 以驗證所有裝置更新的狀態。</span><span class="sxs-lookup"><span data-stu-id="9e607-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="9e607-129">如需裝置更新 Web 服務的詳細資訊，請參閱規劃文件中的〈[View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="9e607-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="9e607-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9e607-130">See also</span></span>

[<span data-ttu-id="9e607-131">匯入-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="9e607-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
