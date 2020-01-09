---
title: '管理商務用 Skype Server 中的電話撥入式會議存取號碼 '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 摘要：瞭解如何在商務用 Skype Server 中管理電話撥入式會議存取號碼。
ms.openlocfilehash: bd2aff1789c040667062d34b8bc037fd0543c029
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991918"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a><span data-ttu-id="d03c2-103">管理商務用 Skype Server 中的電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="d03c2-103">Manage dial-in conferencing access numbers in Skype for Business Server</span></span>
 
<span data-ttu-id="d03c2-104">**摘要：** 瞭解如何在商務用 Skype Server 中管理電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="d03c2-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.</span></span>
  
<span data-ttu-id="d03c2-105">當您部署電話撥入式會議時，您必須設定使用者可從公用交換電話網絡（PSTN）撥打電話的電話號碼，以加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="d03c2-105">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="d03c2-106">這些撥入存取號碼會出現在會議邀請和 [電話撥入式會議設定] 網頁上。</span><span class="sxs-lookup"><span data-stu-id="d03c2-106">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="d03c2-107">本主題說明如何查看、修改或刪除現有的電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="d03c2-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="d03c2-108">如需如何建立初始撥入存取號碼的詳細資訊，請參閱[在商務用 Skype Server 中設定電話撥入式會議](../../deploy/deploy-conferencing/dial-in-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="d03c2-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="d03c2-109">查看電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="d03c2-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="d03c2-110">您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server Management Shell 來查看電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="d03c2-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d03c2-111">使用商務用 Skype Server [控制台] 來查看撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="d03c2-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d03c2-112">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d03c2-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="d03c2-113">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="d03c2-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d03c2-114">在左側導覽列中，按一下 [**會議**]，然後按一下 [**撥入存取號碼**]。</span><span class="sxs-lookup"><span data-stu-id="d03c2-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="d03c2-115">在 [**撥入存取號碼**] 頁面上，按一下您要查看的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="d03c2-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="d03c2-116">在 [**編輯**] 中，選取 [**顯示詳細資料**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d03c2-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d03c2-117">使用商務用 Skype Server Management Shell 來查看撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="d03c2-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="d03c2-118">若要查看電話撥入存取號碼的相關資訊，請使用**CsDialInConferencingAccessNumber** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d03c2-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="d03c2-119">下列命令會傳回已設定為在組織中使用的所有電話撥入式會議存取號碼集合：</span><span class="sxs-lookup"><span data-stu-id="d03c2-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

<span data-ttu-id="d03c2-120">下列是傳回的資訊類型範例：</span><span class="sxs-lookup"><span data-stu-id="d03c2-120">The following is an example of the type of information returned:</span></span>
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

<span data-ttu-id="d03c2-121">如需詳細資訊，請參閱[CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="d03c2-121">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="d03c2-122">修改電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="d03c2-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="d03c2-123">您可以使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype Server Management 命令介面] 來修改撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="d03c2-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d03c2-124">使用商務用 Skype Server [控制台] 修改撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="d03c2-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d03c2-125">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d03c2-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="d03c2-126">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="d03c2-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d03c2-127">在左側導覽列中，按一下 [**會議**]，然後按一下 [**撥入存取號碼**]。</span><span class="sxs-lookup"><span data-stu-id="d03c2-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="d03c2-128">在 [**撥入存取號碼**] 頁面上，按一下清單中的其中一個撥入存取號碼，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="d03c2-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d03c2-129">使用 [搜尋] 欄位來搜尋撥入存取號碼清單中的欄內容，可能不會產生您預期的結果。</span><span class="sxs-lookup"><span data-stu-id="d03c2-129">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="d03c2-130">您可以改為依您想要查看或變更的撥入存取號碼來排序清單。</span><span class="sxs-lookup"><span data-stu-id="d03c2-130">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="d03c2-131">在 [**顯示號碼**] 中，輸入「公用交換電話網絡（PSTN）電話撥打電話給」加入會議的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d03c2-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="d03c2-132">這個數位會顯示在 [會議邀請] 和 [電話撥入式會議設定] 網頁上。</span><span class="sxs-lookup"><span data-stu-id="d03c2-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="d03c2-133">在 [**顯示名稱**] 中，輸入撥入存取號碼的描述。</span><span class="sxs-lookup"><span data-stu-id="d03c2-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="d03c2-134">這是與商務用 Skype 搜尋結果中的撥入存取號碼相關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="d03c2-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="d03c2-135">當使用者呼叫存取號碼時，此名稱就會顯示在用戶端中。</span><span class="sxs-lookup"><span data-stu-id="d03c2-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="d03c2-136">在 [**行 uri**] 中，輸入電話 uri 格式的撥入存取號碼的 E. 164 個數字，包括數位前面的 + 符號，不含空格。</span><span class="sxs-lookup"><span data-stu-id="d03c2-136">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="d03c2-137">例如，電話： + 14255550200。</span><span class="sxs-lookup"><span data-stu-id="d03c2-137">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d03c2-138">其他電話撥入式會議存取號碼無法重複使用相同的行 URI。</span><span class="sxs-lookup"><span data-stu-id="d03c2-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="d03c2-139">在**SIP URI**中，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d03c2-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="d03c2-140">在文字方塊中，輸入此電話撥入式會議存取號碼的唯一 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="d03c2-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="d03c2-141">此 SIP URI 會顯示在不同的位置，包括但不限於呼叫通知訊息及舊版 Lync 用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="d03c2-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d03c2-142">其他電話撥入式會議存取號碼無法重複使用相同的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="d03c2-142">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="d03c2-143">在建立存取號碼之後，便無法修改 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="d03c2-143">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="d03c2-144">變更 SIP URI 的唯一方式是刪除並重新建立存取號碼。</span><span class="sxs-lookup"><span data-stu-id="d03c2-144">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="d03c2-145">在下拉式清單方塊中，按一下支援此撥入存取號碼之會議助理應用程式的網域。</span><span class="sxs-lookup"><span data-stu-id="d03c2-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="d03c2-146">在 [Pool] （**池**）中，按一下執行支援此撥入存取號碼之會議助理實例的池。</span><span class="sxs-lookup"><span data-stu-id="d03c2-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d03c2-147">如果您在建立存取號碼後需要變更池，您必須使用**CsApplicationEndpoint** Cmdlet，或刪除並重新建立存取號碼。</span><span class="sxs-lookup"><span data-stu-id="d03c2-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="d03c2-148">在**主要語言**中，按一下針對此撥入存取號碼播放提示的語言。</span><span class="sxs-lookup"><span data-stu-id="d03c2-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="d03c2-149">主要語言是會議助理用來接聽通話的語言。</span><span class="sxs-lookup"><span data-stu-id="d03c2-149">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="d03c2-150">支援的語言會顯示在電話撥入式會議設定網頁上的每個存取電話號碼旁邊。</span><span class="sxs-lookup"><span data-stu-id="d03c2-150">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="d03c2-151">可選在**次要語言（最多四個）** 中，按一下 [**新增**]，選取您想要支援來電者至此撥入存取號碼的一或多個其他語言，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d03c2-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="d03c2-152">您最多可以為每個撥入存取號碼選擇四個次要語言。</span><span class="sxs-lookup"><span data-stu-id="d03c2-152">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="d03c2-153">使用者在撥入會議時，輸入會議 ID 前，就可以選取次要語言。</span><span class="sxs-lookup"><span data-stu-id="d03c2-153">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="d03c2-154">若要新增撥入存取號碼的地區，請在 [**相關區域**] 底下，按一下 [**新增**]，按一下與此撥入存取號碼的撥號方案相關聯的一個或多個區域，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d03c2-154">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="d03c2-155">若要從撥入存取號碼刪除區域，請在 [**相關區域**] 底下，按一下您要刪除的區域，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="d03c2-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="d03c2-156">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d03c2-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d03c2-157">使用商務用 Skype Server Management Shell 來修改撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="d03c2-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="d03c2-158">若要修改撥入存取號碼，請使用**CsDialInConferencingAccessNumber** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d03c2-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="d03c2-159">下列命令會使用身分識別 sip:RedmondDialIn@litwareinc.com 來修改電話撥入式會議存取號碼的 DisplayName 屬性。</span><span class="sxs-lookup"><span data-stu-id="d03c2-159">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com.</span></span> <span data-ttu-id="d03c2-160">在這個範例中，顯示名稱會設定為「雷德撥入存取號碼」：</span><span class="sxs-lookup"><span data-stu-id="d03c2-160">In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

<span data-ttu-id="d03c2-161">在下一個範例中，含有身分識別 sip:RedmondDialIn@litwareinc.com 的電話撥入式會議存取號碼已修改，以包含兩個地區：雷蒙德與北京。</span><span class="sxs-lookup"><span data-stu-id="d03c2-161">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle.</span></span> <span data-ttu-id="d03c2-162">若要這樣做，請先呼叫 [地區] 參數，接著再加上兩個區域（以逗號分隔的兩個字串值）。</span><span class="sxs-lookup"><span data-stu-id="d03c2-162">To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas).</span></span> <span data-ttu-id="d03c2-163">請注意，除非雷德蒙及西雅圖地區都已在撥號方案中定義，否則此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="d03c2-163">Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

<span data-ttu-id="d03c2-164">如需詳細資訊，請參閱[設定 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="d03c2-164">For more information, see [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="d03c2-165">刪除電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="d03c2-165">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="d03c2-166">您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server 管理命令介面，刪除電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="d03c2-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d03c2-167">使用商務用 Skype Server [控制台] 刪除電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="d03c2-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="d03c2-168">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="d03c2-168">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="d03c2-169">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="d03c2-169">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d03c2-170">在左側導覽列中，按一下 [**會議**]，然後按一下 [**撥入存取號碼**]。</span><span class="sxs-lookup"><span data-stu-id="d03c2-170">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="d03c2-171">在頁面上，按一下清單中您要刪除的撥入號碼，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="d03c2-171">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="d03c2-172">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d03c2-172">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d03c2-173">使用商務用 Skype Server Management Shell 刪除電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="d03c2-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="d03c2-174">若要刪除電話撥入式會議存取號碼，請使用 [**移除-CsDialInConferencingAccessNumber**]。</span><span class="sxs-lookup"><span data-stu-id="d03c2-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="d03c2-175">下列命令會刪除含身分識別 sip:RedmondDialInAccess@litwareinc.com 的電話撥入式會議存取號碼：</span><span class="sxs-lookup"><span data-stu-id="d03c2-175">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="d03c2-176">[下一步] 命令會刪除與西北地方相關的所有電話撥入式會議存取號碼：</span><span class="sxs-lookup"><span data-stu-id="d03c2-176">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="d03c2-177">[下一步] 命令會刪除所有以義大利為主要語言的電話撥入式會議存取號碼：</span><span class="sxs-lookup"><span data-stu-id="d03c2-177">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="d03c2-178">如需詳細資訊，請參閱[移除-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="d03c2-178">For more information, see [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  

