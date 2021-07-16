---
title: 決定如何在解除委任之後管理屬性
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本文說明如何在解除委任您的內部部署環境之後管理屬性。
ms.openlocfilehash: 1c862e8c0055fc2eb40efcc7d26bb9a1166ae550
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458983"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a><span data-ttu-id="15550-103">決定如何在解除委任之後管理屬性</span><span class="sxs-lookup"><span data-stu-id="15550-103">Decide how to manage attributes after decommissioning</span></span>

<span data-ttu-id="15550-104">根據預設，先前為商務用 Skype Server 啟用之後又移至雲端的所有使用者，仍然會在您的內部部署 Active Directory 中設定 msRTCSIP 屬性。</span><span class="sxs-lookup"><span data-stu-id="15550-104">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> 

<span data-ttu-id="15550-105">這些屬性在特定 sip 位址 (msRTCSIP-PrimaryUserAddress) 和可能的電話號碼 (msRTCSIP 行) ，請繼續同步處理至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="15550-105">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="15550-106">如果需要變更任何 msRTCSIP 屬性，必須在內部部署 Active Directory 中進行這些變更，然後同步處理至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="15550-106">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="15550-107">不過，商務用 Skype Server 部署已移除之後，就無法使用商務用 Skype Server 工具來管理這些屬性。</span><span class="sxs-lookup"><span data-stu-id="15550-107">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="15550-108">有兩個選項可用於處理這種情況：</span><span class="sxs-lookup"><span data-stu-id="15550-108">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="15550-109">保留已為商務用 Skype 伺服器帳戶啟用的使用者，並使用 Active Directory 工具管理 msRTCSIP 屬性。</span><span class="sxs-lookup"><span data-stu-id="15550-109">Leave users that were enabled for Skype for Business server accounts as is, and manage the msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="15550-110">這可確保已遷移使用者沒有服務遺失，而且可讓您透過消除 (（例如，擦除) 伺服器，而不需完全退役）來輕鬆移除商務用 Skype Server 部署。</span><span class="sxs-lookup"><span data-stu-id="15550-110">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="15550-111">不過，新授權的使用者將不會在您的內部部署 Active Directory 中填入這些屬性，且必須在線上進行管理。</span><span class="sxs-lookup"><span data-stu-id="15550-111">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="15550-112">從內部部署 Active Directory 中已遷移的使用者清除所有 msRTCSIP 屬性，並使用線上工具管理這些屬性。</span><span class="sxs-lookup"><span data-stu-id="15550-112">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="15550-113">這個方法可讓現有和新使用者使用一致的管理方法，但在內部部署解除委任程式中，可能會導致服務暫時遺失。</span><span class="sxs-lookup"><span data-stu-id="15550-113">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="15550-114">方法 1-管理 Active Directory 中使用者的 sip 位址和電話號碼</span><span class="sxs-lookup"><span data-stu-id="15550-114">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="15550-115">管理員可以管理先前已從內部部署商務用 Skype Server 移至雲端的使用者，即使已解除內部部署的部署也是一樣。</span><span class="sxs-lookup"><span data-stu-id="15550-115">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> 

<span data-ttu-id="15550-116">若要變更使用者的 sip 位址或使用者的電話號碼 (而且 sip 位址或電話號碼在內部部署 Active Directory) 中已有值，您必須在內部部署 Active Directory 中執行這項作業，並讓) 流向 Azure AD 的值 (s。</span><span class="sxs-lookup"><span data-stu-id="15550-116">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="15550-117">這不需要內部部署商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="15550-117">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="15550-118">相反地，您可以使用 Active Directory 使用者和電腦 MMC 嵌入式管理單元來直接修改內部部署 Active Directory 中的這些屬性 (，如) 所示，或是使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="15550-118">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="15550-119">如果您使用的是 MMC 嵌入式管理單元，請開啟使用者的 [屬性] 頁面，按一下 [屬性編輯器] 索引標籤，然後尋找適當的屬性進行修改：</span><span class="sxs-lookup"><span data-stu-id="15550-119">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="15550-120">若要修改使用者的 sip 位址，請修改 `msRTCSIP-PrimaryUserAddress` 。</span><span class="sxs-lookup"><span data-stu-id="15550-120">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="15550-121">如果 `ProxyAddresses` 屬性包含 sip 位址，也會將此值更新為最佳作法。</span><span class="sxs-lookup"><span data-stu-id="15550-121">If the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="15550-122">雖然所填入的 sip 位址 `ProxyAddresses` 已在 O365 中忽略，但 `msRTCSIP-PrimaryUserAddress` 其他內部部署元件也可以使用它。</span><span class="sxs-lookup"><span data-stu-id="15550-122">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="15550-123">若要修改使用者的電話號碼，請修改 `msRTCSIP-Line` *是否已有值*。</span><span class="sxs-lookup"><span data-stu-id="15550-123">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Active Directory 使用者和電腦工具](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="15550-125">如果使用者在 `msRTCSIP-Line` 移動之前沒有內部部署的值，您可以使用 `onpremLineUri` 商務用 Skype 線上 PowerShell 模組中[Set-CsUser Cmdlet](/powershell/module/skype/set-csuser?view=skype-ps)中的-參數修改電話號碼。</span><span class="sxs-lookup"><span data-stu-id="15550-125">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="15550-126">在您停用混合式之後所建立的新使用者，這些使用者不需要這些步驟，而且可以直接在雲端中管理這些使用者。</span><span class="sxs-lookup"><span data-stu-id="15550-126">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="15550-127">如果您習慣使用這些方法的組合，以及在內部部署 Active Directory 中就地保留 msRTCSIP 屬性，則可以直接重新鏡像內部部署商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="15550-127">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="15550-128">不過，如果您想要清除所有 msRTCSIP 屬性，並執行商務用 Skype Server 的傳統卸載，請使用方法2。</span><span class="sxs-lookup"><span data-stu-id="15550-128">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="15550-129">方法 2-清除 Active Directory 中所有內部部署使用者的商務用 Skype 屬性</span><span class="sxs-lookup"><span data-stu-id="15550-129">Method 2 - Clear Skype for Business attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="15550-130">這個選項需要額外的工作量並適當地規劃，因為先前已從內部部署商務用 Skype Server 移至雲端的使用者需要重新布建。</span><span class="sxs-lookup"><span data-stu-id="15550-130">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="15550-131">這些使用者可以分為兩種不同的類別：沒有電話系統的使用者和具有電話系統的使用者。</span><span class="sxs-lookup"><span data-stu-id="15550-131">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="15550-132">在將電話號碼從內部部署 Active Directory 中管理到雲端時，具有電話系統的使用者將會經歷暫時遺失電話語音的情況。</span><span class="sxs-lookup"><span data-stu-id="15550-132">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="15550-133">**建議您在開始大量使用者作業之前，先使用少量的使用者與電話系統執行試驗。**</span><span class="sxs-lookup"><span data-stu-id="15550-133">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="15550-134">對於大型部署，使用者可以在不同時間視窗的較小群組中處理。</span><span class="sxs-lookup"><span data-stu-id="15550-134">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="15550-135">此程式最簡單的情況是具有相符 sip 位址及 UserPrincipalName 的使用者。</span><span class="sxs-lookup"><span data-stu-id="15550-135">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="15550-136">如果組織的使用者在這兩個屬性之間具有非符合性值，請特別注意，以順利進行轉換。</span><span class="sxs-lookup"><span data-stu-id="15550-136">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="15550-137">如果您已設定自動語音應答或通話佇列的內部部署混合應用程式端點，請務必在解除委任商務用 Skype Server 之前，將這些端點移至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="15550-137">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="15550-138">確認下列內部部署商務用 Skype PowerShell Cmdlet 會傳回空的結果。</span><span class="sxs-lookup"><span data-stu-id="15550-138">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="15550-139">空的結果表示沒有使用者位於內部部署，且已移至 Microsoft 365 或已停用：</span><span class="sxs-lookup"><span data-stu-id="15550-139">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="15550-140">執行下列內部部署商務用 Skype Server PowerShell Cmdlet 以匯出使用者資料，以記錄使用者的目前電話號碼 (LineUri) 、UserPrincipalName 及相關資訊：</span><span class="sxs-lookup"><span data-stu-id="15550-140">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="15550-141">繼續開啟 SfbUserSettings.csv 的檔案，並確認所有使用者資料都已成功匯出之前。</span><span class="sxs-lookup"><span data-stu-id="15550-141">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="15550-142">建議保留此檔案的副本。</span><span class="sxs-lookup"><span data-stu-id="15550-142">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="15550-143">請勿在下列步驟中將此檔案用於處理使用者。</span><span class="sxs-lookup"><span data-stu-id="15550-143">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="15550-144">使用下列步驟建立包含一組使用者的檔案。</span><span class="sxs-lookup"><span data-stu-id="15550-144">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="15550-145">在第一組使用者成功完成之後，請繼續進行下一組使用者。</span><span class="sxs-lookup"><span data-stu-id="15550-145">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="15550-146">在下列範例中，會依字母順序選取使用者群組，但您可以依據符合您要處理使用者之方式的準則來篩選使用者。</span><span class="sxs-lookup"><span data-stu-id="15550-146">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="15550-147">繼續開啟的 SfbUsers.csv 檔案，並確認已順利匯出使用者資料。</span><span class="sxs-lookup"><span data-stu-id="15550-147">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="15550-148">在稍後的步驟中，您將需要 LineUri (電話號碼) 、UserPrincipalName、SamAccountName 和 SipAddress。</span><span class="sxs-lookup"><span data-stu-id="15550-148">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="15550-149">針對您準備更新的使用者集合，從 active Directory 中刪除與商務用 Skype Server 相關的屬性資訊。</span><span class="sxs-lookup"><span data-stu-id="15550-149">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="15550-150">此處理程式有兩個步驟，如下所示。</span><span class="sxs-lookup"><span data-stu-id="15550-150">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="15550-151">在執行此步驟後的下一個 AAD 同步週期之後，具有先前從內部部署商務用 Skype Server 移至雲端的電話系統使用者將無法進行呼叫，直到步驟8成功完成並確認步驟9中。</span><span class="sxs-lookup"><span data-stu-id="15550-151">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="15550-152">此外，請確定您已將使用者的電話號碼和相關資訊儲存為步驟2，因為該步驟需要該資訊。</span><span class="sxs-lookup"><span data-stu-id="15550-152">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="15550-153">接下來，針對同一組使用者，使用內部部署 Active Directory PowerShell: 清除 msRTCSIP-DeploymentLocator 的值</span><span class="sxs-lookup"><span data-stu-id="15550-153">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="15550-154">針對 Windows PowerShell Cmdlet 執行下列內部部署 active directory 模組，將 sip 位址值新增回內部部署 Active directory proxyAddresses。</span><span class="sxs-lookup"><span data-stu-id="15550-154">Run the following on-premise Active Directory Module for Windows PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="15550-155">這會防止依賴此屬性的互通性問題。</span><span class="sxs-lookup"><span data-stu-id="15550-155">This will prevent interoperability issues that rely on this attribute.</span></span> 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. <span data-ttu-id="15550-156">執行 Azure AD 同步</span><span class="sxs-lookup"><span data-stu-id="15550-156">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="15550-157">等候使用者布建完成。</span><span class="sxs-lookup"><span data-stu-id="15550-157">Wait for user provisioning to complete.</span></span> <span data-ttu-id="15550-158">您可以執行下列商務用 Skype 線上 PowerShell 命令，以監視使用者布建進度。</span><span class="sxs-lookup"><span data-stu-id="15550-158">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="15550-159">下列商務用 Skype 線上 PowerShell 命令會在很快的處理常式完成時傳回空的結果。</span><span class="sxs-lookup"><span data-stu-id="15550-159">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="15550-160">執行下列商務用 Skype 線上 PowerShell 命令指派電話號碼，並為使用者啟用電話系統：</span><span class="sxs-lookup"><span data-stu-id="15550-160">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  <span data-ttu-id="15550-161">如果您仍然有商務用 Skype 端點 (Skype 用戶端或協力廠商電話) ，您也會想要將 HostedVoiceMail 設定為 $true。</span><span class="sxs-lookup"><span data-stu-id="15550-161">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="15550-162">如果您的組織只對啟用語音的使用者使用 Teams 端點，則此設定不適用於您的使用者。</span><span class="sxs-lookup"><span data-stu-id="15550-162">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="15550-163">確認已正確布建電話系統功能的使用者。</span><span class="sxs-lookup"><span data-stu-id="15550-163">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="15550-164">下列商務用 Skype 線上 PowerShell 命令會在很快的處理常式完成時傳回空的結果。</span><span class="sxs-lookup"><span data-stu-id="15550-164">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. <span data-ttu-id="15550-165">重複步驟3到9，直到處理所有使用者為止。</span><span class="sxs-lookup"><span data-stu-id="15550-165">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="15550-166">執行下列兩個 PowerShell 命令，確認已成功處理所有使用者。</span><span class="sxs-lookup"><span data-stu-id="15550-166">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="15550-167">內部部署商務用 Skype Server 內部部署 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="15550-167">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="15550-168">商務用 Skype線上 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="15550-168">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="15550-169">在方法2中完成所有步驟之後，請參閱[將混合應用程式端點從內部部署移至線上](decommission-move-on-prem-endpoints.md)，並[移除內部部署商務用 Skype Server](decommission-remove-on-prem.md) ，以取得其他步驟，以移除您的商務用 Skype Server 內部部署。</span><span class="sxs-lookup"><span data-stu-id="15550-169">After you have completed all steps in Method 2, see [Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) and [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="15550-170">請參閱</span><span class="sxs-lookup"><span data-stu-id="15550-170">See also</span></span>

- [<span data-ttu-id="15550-171">Teams 與商務用 Skype 的雲整合</span><span class="sxs-lookup"><span data-stu-id="15550-171">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="15550-172">解除您的內部部署商務用 Skype 環境</span><span class="sxs-lookup"><span data-stu-id="15550-172">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

