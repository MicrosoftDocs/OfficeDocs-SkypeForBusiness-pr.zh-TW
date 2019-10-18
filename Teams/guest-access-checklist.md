---
title: Microsoft 團隊來賓存取檢查清單
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: 使用此檢查清單可協助您設定 Microsoft 團隊中的來賓存取權。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e7f019f2260b1e86b422f8b4238439fbd2f1607a
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569542"
---
<a name="teams-guest-access-checklist"></a>小組訪客存取檢查清單
==========================================

您可以根據貴組織的喜好設定，使用此檢查清單來協助您啟用及設定 Microsoft 團隊中的來賓存取功能。

> [!NOTE] 
> 針對共同作業限制，請參閱[啟用 B2B 外部共同作業和管理可邀請來賓的人員](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。

## <a name="understand-the-limitations-for-guests"></a>瞭解來賓的限制

來賓體驗會依設計而有所限制。 請務必瞭解來賓體驗，不要嘗試修正不存在問題的內容。 例如，以下是 Microsoft 團隊中的來賓無法使用的一些功能清單：

- 商務用 OneDrive
- 團隊外的人員搜尋
- 行事曆、排程的會議或會議詳細資料
- 通向
- 組織結構
- 建立或修改團隊
- 流覽團隊
- 將檔案上傳到人員對人聊天
- 如果訪客知道使用者的完整電子郵件識別碼，就能繼續搜尋並尋找他們的小組外的使用者。 若要避免這種情況，IT 系統管理員可以使用可將來賓限制在自己的虛擬 GAL 中的模式，例如已設定[目錄搜尋的範圍](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search)。

如需詳細資訊，請參閱[Office 365 群組中](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)[的來賓體驗是什麼](guest-experience.md)，以及來賓存取權。

### <a name="guest-access-vs-external-access-federation"></a>來賓存取與外部存取（同盟）

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> 目前，Microsoft 團隊不支援來賓 inviter 角色。 在 Microsoft 團隊中，您至少必須將 [成員可以邀請] 切換開關設定為 [是]，才能使用來賓存取。 如果您將「成員可以邀請」設定為 [否]，然後在 Office 365 群組和 Microsoft 團隊中啟用來賓存取，系統管理員可以控制您的目錄的來賓邀請。 來賓在目錄中後，就可以由非系統管理員成員，將它們新增至小組。

## <a name="if-your-guests-are-seeing-license-errors"></a>如果您的客人看到授權錯誤

Microsoft 團隊中的來賓存取使用 Azure Active Directory （Azure AD）商務用企業（B2B）和授權模型。 如果您看到授權錯誤，請務必閱讀[B2B 授權指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)，瞭解貴組織擁有的授權需求，讓您的使用者能夠邀請來賓加入您的組織。

請記住下列事項：

- 來賓是您組織外部的使用者。 您的員工、現場承包商、現場代理商等不能新增為來賓。 同樣適用于您的公司。
- 來賓授權會根據邀請的組織數來計算。 當您計算所需的授權數量時，請考慮這麼做。
- 無論受邀者是來自另一個 Office 365 租使用者，還是正在使用其個人電子郵件地址，都會針對您的組織計算授權。

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a>□步驟1：設定 Azure AD 企業對企業中的設定

1. 以租使用者管理員的身分登入[Azure 入口網站](https://portal.azure.com)。
2. 選取 [ **Azure Active Directory** > **使用者** > ]**使用者設定**。
3. 在 [**外部使用者**] 底下，選取 [**管理外部**共同作業設定]。
   > [!NOTE]
   > 您也可以從 [**組織關聯**] 頁面取得外部共同作業**設定**。 在 Azure Active Directory 中的 [**管理**] 底下，移至 [**組織關聯** > ]**設定**。
4. 在 [**外部**共同作業設定] 頁面上，選擇您要啟用的原則。

  - **來賓使用者許可權有限**：此原則會判斷您目錄中來賓的許可權。 選取 **[是]** 來封鎖特定目錄工作的訪客，例如列舉使用者、群組或其他目錄資源。 選取 [**否**]，為來賓提供與目錄中的一般使用者相同的目錄資料存取權。
   - **來賓 inviter 角色中的管理員和使用者可以邀請**：若要允許「來賓 inviter」角色中的系統管理員和使用者邀請客人，請將此原則設定為 **[是]**。
   - **成員可以邀請**：若要允許目錄的非系統管理員成員邀請客人，請將此原則設定為 **[是]**。
   
       > [!NOTE]
       > 如果您設定 [**成員可以**在 Office 365 群組和 Microsoft 團隊中邀請您**不**想再啟用來賓存取]，系統管理員可以控制您的目錄的來賓邀請。 來賓在目錄中後，就可以由非系統管理員成員，將它們新增至小組。 如需詳細資訊，請參閱[授權 Microsoft 團隊中的來賓存取](Teams-dependencies.md)。
   
   - **客人可以邀請**：若要讓客人邀請其他客人，請將此原則設定為 **[是]**。
   - **啟用電子郵件的一次性密碼（預覽版）**：如需一次性密碼功能的詳細資訊，請參閱[電子郵件一次性密碼驗證（預覽版）](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)。

   - 共同作業**限制**：如需有關允許或封鎖特定網域之邀請的詳細資訊，請參閱[允許或封鎖來自特定組織的 B2B 使用者邀請](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。
    
## <a name="-step-2-configure-office-365-groups"></a>□步驟2：設定 Office 365 群組

1. 在 Microsoft 365 系統管理中心，移至 [**設定** > **服務] & [增益集** > ]**Office 365 群組**。
2. 確認將**組織存取群組內容外的群組成員**設定為 [**開啟**]。 如果關閉此設定，來賓將無法存取任何群組內容。
3. 確認 **[允許群組擁有者將組織外部的人員新增至群組**] 已設定為 [**開啟**]。 如果關閉此設定，小組擁有者將無法新增來賓。 此設定至少必須開啟才能支援來賓存取。

     ![螢幕擷取畫面顯示 Office 365 群組的切換](media/guest-access-checklist-office365.png)

如需設定這些設定的詳細指示，請參閱[管理 office 365 群組中的來賓存取](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)，以及[控制 office 365 群組中的來賓存取權](Teams-dependencies.md#control-guest-access-in-office-365-groups)。
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a>□步驟3：啟用租使用者層級的來賓存取權

您必須至少針對**Microsoft 團隊系統管理中心**的 microsoft 團隊開啟來賓存取權。 

1. 在 [團隊管理中心] 中，選取 [全**組織性設定** > **來賓存取**]。
2. 將 [**允許 Microsoft 團隊中的來賓存取權**] 切換為 [**開啟**]。

    ![螢幕擷取畫面顯示 [團隊設定] 切換開關的範例](media/guest-access-checklist-set-up-guests-image1.png)

3. 在此相同頁面上，設定您所需的任何其他來賓設定。
4. 按一下 [**儲存**]。

如需詳細指示，請參閱[開啟或關閉 Microsoft 團隊的來賓存取權](set-up-guests.md)。


## <a name="--step-4-configure-sharing-in-office-365"></a>□步驟4：在 Office 365 中設定共用 

請確定使用者可以新增來賓。 做法如下：

1. 在 Microsoft 365 系統管理中心中，移至 [**設定** > **安全性] & [隱私權**]。

     ![螢幕擷取畫面顯示服務設定的範例](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. 在 [**共用**] 中，選取 [**編輯**]。

     ![螢幕擷取畫面顯示共用設定切換的範例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. 設定 [**讓使用者將新的來賓新增至此組織** **]，然後**按一下 [**儲存**]。

     ![螢幕擷取畫面顯示共用設定切換的範例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> 這個設定相當於 Azure AD 中的 [**使用者設定** > **] 中的**[**成員可以邀請**] 設定。  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a>□步驟5：驗證 SharePoint 中的共用設定

1. 登入 Microsoft 365 系統管理中心。
2. 按一下 [系統**管理中心**]，然後選取 [ **SharePoint**]。
3. 在 SharePoint 系統管理中心中，選取 [**共用**]。
4. 確定*沒有*選取 [不**允許在您的組織外共用**] 選項。
 
     ![螢幕擷取畫面顯示 SparePoint Online 設定切換開關的範例。](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a>□步驟6：啟用頻道的特定設定 

在團隊應用程式的個別小組層級，設定來賓許可權，讓來賓可以建立、更新及刪除頻道。 除了管理員之外，小組擁有者還可以設定此設定。

![螢幕擷取畫面顯示 [團隊/頻道設定] 切換開關的範例](media/guest-access-checklist-TeamsSettings2.png)

如需詳細資訊（包括操作說明影片），請參閱[Microsoft 團隊中的來賓存取權](guest-access.md)。


## <a name="troubleshooting"></a>疑難排解

如果您在 Microsoft 團隊中新增來賓時遇到問題，請參閱[來賓存取疑難排解指南](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)。


