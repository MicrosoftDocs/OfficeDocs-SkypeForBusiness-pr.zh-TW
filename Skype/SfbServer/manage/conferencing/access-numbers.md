---
title: '管理商務用 Skype Server 中的電話撥入式會議存取號碼 '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 摘要：瞭解如何管理商務用 Skype Server 中的電話撥入式會議存取號碼。
ms.openlocfilehash: 4008293015beaa684f9a3d9fa0ec0dedf05e5b2b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099149"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a><span data-ttu-id="182d9-103">管理商務用 Skype Server 中的電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="182d9-103">Manage dial-in conferencing access numbers in Skype for Business Server</span></span>
 
<span data-ttu-id="182d9-104">**摘要：** 瞭解如何管理商務用 Skype Server 中的電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="182d9-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.</span></span>
  
<span data-ttu-id="182d9-105">當您部署電話撥入式會議時，您必須設定使用者可以從公用交換電話網路 (PSTN) 撥打的電話號碼，以加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="182d9-105">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="182d9-106">這些撥入存取號碼會顯示在會議邀請和電話撥入式會議設定網頁上。</span><span class="sxs-lookup"><span data-stu-id="182d9-106">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="182d9-107">本主題說明如何查看、修改或刪除現有的電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="182d9-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="182d9-108">如需如何建立初始撥入存取號碼的詳細資訊，請參閱 [在商務用 Skype Server 中設定電話撥入式會議](../../deploy/deploy-conferencing/dial-in-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="182d9-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="182d9-109">查看電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="182d9-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="182d9-110">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來查看電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="182d9-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="182d9-111">使用商務用 Skype Server 控制台來查看撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="182d9-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="182d9-112">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="182d9-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="182d9-113">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="182d9-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="182d9-114">在左導覽列中，按一下 [會議]，然後按一下 [撥入存取號碼]。</span><span class="sxs-lookup"><span data-stu-id="182d9-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="182d9-115">在 **[撥入存取號碼]** 頁面中，按一下要檢視的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="182d9-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="182d9-116">在 [ **編輯**] 中，選取 [ **顯示詳細資料** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="182d9-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="182d9-117">使用商務用 Skype Server 管理命令介面來查看撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="182d9-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="182d9-118">若要查看撥入存取號碼的資訊，請使用 **Get-CsDialInConferencingAccessNumber** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="182d9-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="182d9-119">下列命令會傳回設定供組織使用之所有電話撥入式會議存取號碼的集合：</span><span class="sxs-lookup"><span data-stu-id="182d9-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

<span data-ttu-id="182d9-120">以下是傳回之資訊類型的範例：</span><span class="sxs-lookup"><span data-stu-id="182d9-120">The following is an example of the type of information returned:</span></span>
  
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

<span data-ttu-id="182d9-121">如需詳細資訊，請參閱 [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="182d9-121">For more information, see [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="182d9-122">修改電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="182d9-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="182d9-123">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來修改撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="182d9-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="182d9-124">使用商務用 Skype Server 控制台修改撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="182d9-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="182d9-125">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="182d9-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="182d9-126">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="182d9-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="182d9-127">在左導覽列中，按一下 [會議]，然後按一下 [撥入存取號碼]。</span><span class="sxs-lookup"><span data-stu-id="182d9-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="182d9-128">在 [ **撥入存取號碼** ] 頁面上，按一下清單中的其中一個撥入存取號碼，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="182d9-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="182d9-p103">使用搜尋欄位來搜尋撥入存取號碼清單中可能無法產生預期結果的欄內容。請依照您想要的欄排序此清單，找出您想檢視或變更的撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="182d9-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="182d9-131">在 [ **顯示號碼**] 中，輸入公用交換電話網路 (PSTN) 電話使用者撥號以加入會議的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="182d9-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="182d9-132">此號碼會顯示在會議邀請中和電話撥入式會議設定網頁上。</span><span class="sxs-lookup"><span data-stu-id="182d9-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="182d9-133">在 [ **顯示名稱**] 中，輸入撥入存取號碼的描述。</span><span class="sxs-lookup"><span data-stu-id="182d9-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="182d9-134">這是商務用 Skype 搜尋結果中與撥入存取號碼相關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="182d9-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="182d9-135">當使用者呼叫存取號碼時，此名稱會顯示在用戶端中。</span><span class="sxs-lookup"><span data-stu-id="182d9-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="182d9-136">在 [ **行 uri**] 中，輸入電話 uri 格式的撥入存取號碼的 e.164 號碼，包含號碼前面的 + 符號，並排除空格。</span><span class="sxs-lookup"><span data-stu-id="182d9-136">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="182d9-137">例如電話： + 14255550200。</span><span class="sxs-lookup"><span data-stu-id="182d9-137">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="182d9-138">其他電話撥入式會議存取號碼無法重複使用相同的列 URI。</span><span class="sxs-lookup"><span data-stu-id="182d9-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="182d9-139">在 [ **SIP URI**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="182d9-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="182d9-140">在文字方塊中，輸入此撥入式會議存取號碼的唯一 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="182d9-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="182d9-141">這種 SIP URI 會顯示在不同的位置，包括（但不限於）來電通知訊息和舊版的 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="182d9-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="182d9-142">其他電話撥入式會議存取號碼無法重複使用相同的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="182d9-142">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="182d9-143">建立存取號碼之後，便無法修改 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="182d9-143">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="182d9-144">變更 SIP URI 的唯一方法是刪除並重新建立存取號碼。</span><span class="sxs-lookup"><span data-stu-id="182d9-144">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="182d9-145">在下拉式清單方塊中，按一下支援此撥入存取號碼之會議應答應用程式的網域。</span><span class="sxs-lookup"><span data-stu-id="182d9-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="182d9-146">在 [ **集** 區] 中，按一下執行支援此撥入存取號碼之會議助理實例的集區。</span><span class="sxs-lookup"><span data-stu-id="182d9-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="182d9-147">如果您在建立存取號碼之後需要變更集區，則必須使用 **Move-CsApplicationEndpoint** Cmdlet，或刪除並重新建立存取號碼。</span><span class="sxs-lookup"><span data-stu-id="182d9-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="182d9-148">在 [ **主要語言**] 中，按一下為此撥入存取號碼播放提示時所使用的語言。</span><span class="sxs-lookup"><span data-stu-id="182d9-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="182d9-149">主要語言是會議助理用來接聽通話的語言。</span><span class="sxs-lookup"><span data-stu-id="182d9-149">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="182d9-150">在 [電話撥入式會議設定] 網頁上的每一個存取電話號碼旁會顯示支援的語言。</span><span class="sxs-lookup"><span data-stu-id="182d9-150">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="182d9-151"> (選用) 在 **次要語言中 (最多四個)**，請按一下 [ **新增**]，選取您要支援的來電者撥打此撥入存取號碼的一或多個其他語言，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="182d9-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="182d9-152">您最多可以為每個撥入存取號碼選擇四種次要語言。</span><span class="sxs-lookup"><span data-stu-id="182d9-152">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="182d9-153">使用者在撥入會議時，可以先選取次要語言，再進入會議識別碼。</span><span class="sxs-lookup"><span data-stu-id="182d9-153">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="182d9-154">若要新增撥入存取號碼的地區，請在 [ **關聯的地區**] 下，按一下 [ **新增**]，然後按一下與此撥入存取號碼的撥號對應表相關聯的一個或多個地區，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="182d9-154">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="182d9-155">若要從撥入存取號碼中刪除地區，請在 [ **關聯的地區**] 下，按一下您要刪除的地區，然後按一下 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="182d9-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="182d9-156">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="182d9-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="182d9-157">使用商務用 Skype Server 管理命令介面來修改撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="182d9-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="182d9-158">若要修改撥入存取號碼，請使用 **Set-CsDialInConferencingAccessNumber** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="182d9-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="182d9-159">下列命令會以 Identity sip:RedmondDialIn@litwareinc.com 修改電話撥入式會議存取號碼的 DisplayName 屬性。</span><span class="sxs-lookup"><span data-stu-id="182d9-159">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com.</span></span> <span data-ttu-id="182d9-160">在此範例中，顯示名稱設為 "Redmond Dial-In 存取號碼"：</span><span class="sxs-lookup"><span data-stu-id="182d9-160">In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

<span data-ttu-id="182d9-161">在下一個範例中，會修改身分識別 sip:RedmondDialIn@litwareinc.com 的電話撥入式會議存取號碼，以包含兩個地區： Redmond 和西雅圖。</span><span class="sxs-lookup"><span data-stu-id="182d9-161">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle.</span></span> <span data-ttu-id="182d9-162">為達此目的，會先呼叫 Region 參數，然後是兩個地區 (以逗號分隔的兩個字串值)。</span><span class="sxs-lookup"><span data-stu-id="182d9-162">To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas).</span></span> <span data-ttu-id="182d9-163">請注意，除非已經在撥號對應表中定義 Redmond 和 Seattle 地區，否則這個命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="182d9-163">Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

<span data-ttu-id="182d9-164">如需詳細資訊，請參閱 [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="182d9-164">For more information, see [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="182d9-165">刪除電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="182d9-165">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="182d9-166">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來刪除電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="182d9-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="182d9-167">使用商務用 Skype Server 控制台刪除電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="182d9-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="182d9-168">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="182d9-168">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="182d9-169">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="182d9-169">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="182d9-170">在左導覽列中，按一下 [會議]，然後按一下 [撥入存取號碼]。</span><span class="sxs-lookup"><span data-stu-id="182d9-170">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="182d9-171">在頁面中，按一下清單中要刪除的撥入號碼，按一下 **[編輯]**，再按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="182d9-171">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="182d9-172">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="182d9-172">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="182d9-173">使用商務用 Skype Server 管理命令介面來刪除電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="182d9-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="182d9-174">若要刪除電話撥入式會議存取號碼，請使用 **Remove-CsDialInConferencingAccessNumber**。</span><span class="sxs-lookup"><span data-stu-id="182d9-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="182d9-175">下列命令會刪除具有 Identity sip:RedmondDialInAccess@litwareinc.com 的電話撥入式會議存取號碼：</span><span class="sxs-lookup"><span data-stu-id="182d9-175">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="182d9-176">下一個命令會刪除與西北地方相關聯的所有電話撥入式會議存取號碼：</span><span class="sxs-lookup"><span data-stu-id="182d9-176">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="182d9-177">下一個命令會刪除所有以義大利文言為主要語言的電話撥入式會議存取號碼：</span><span class="sxs-lookup"><span data-stu-id="182d9-177">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="182d9-178">如需詳細資訊，請參閱 [Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="182d9-178">For more information, see [Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
