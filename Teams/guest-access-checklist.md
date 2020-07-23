---
title: Microsoft 團隊來賓存取檢查清單
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: 瞭解如何在 Microsoft 團隊中開啟和設定來賓存取（作為全域或團隊管理員）。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d38b0adf1a342c4398d2779e2f0b5ec3aa310144
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372002"
---
<a name="microsoft-teams-guest-access-checklist"></a>Microsoft 團隊來賓存取檢查清單
=========================================

使用此檢查清單可協助您開啟並設定 Microsoft 團隊中的來賓存取權。 您必須是全域系統管理員或團隊管理員，才能進行這些變更。

> [!IMPORTANT]
> 您可能需要等候幾個小時，變更才會生效。

觀看這段短片（5:31 分鐘），瞭解如何在整個 Microsoft 365 （包括團隊）中開啟來賓存取。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a>步驟1：在團隊的整個組織層級開啟來賓存取

您必須是團隊服務管理員，才能進行這些變更。 請參閱[使用團隊管理員角色管理團隊](https://docs.microsoft.com/microsoftteams/using-admin-roles)，瞭解如何取得管理員角色和許可權。

1. 在 [團隊管理中心] 中，選取 [全**組織性設定**  >  **來賓存取**]。
2. 將 [**允許 Microsoft 團隊中的來賓存取權**] 切換為 [**開啟**]。

    ![螢幕擷取畫面顯示 [團隊設定] 切換開關的範例](media/guest-access-checklist-set-up-guests-image1.png)

3. 在此相同頁面上，開啟或關閉來賓的**通話**、**會議**和**訊息**設定。
4. 按一下 [儲存]****。

> [!TIP]
> 如果您使用的是 Azure Active Directory、SharePoint Online 和 Microsoft 365 群組中的預設設定，您可能已完成來賓存取。 在這種情況下，您可以略過其餘的步驟。 如果您不確定，或者您使用的是 AAD、SharePoint Online 或 Microsoft 365 群組的自訂設定，請繼續執行此檢查清單中的其餘步驟。

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a>步驟2：設定 Azure AD 企業對企業設定

這些是支援小組中來賓存取權的 Azure AD 設定。 設定好這些設定之後，您就可以在小組中[新增](add-guests.md)和[管理來賓](manage-guests.md)。

1. 以租使用者管理員的身分登入[Azure 入口網站](https://portal.azure.com)。
2. 選取 [ **Azure Active Directory**  >  **使用者**]  >  **使用者設定**。
3. 在 [**外部使用者**] 底下，選取 [**管理外部**共同作業設定]。
   > [!NOTE]
   > 您也可以從 [**組織關聯**] 頁面取得外部共同作業**設定**。 在 Azure Active Directory 中的 [**管理**] 底下，移至 [**組織關聯**]  >  **設定**。
4. 在 [**外部**共同作業設定] 頁面上，選擇您要啟用的原則。

    - **來賓使用者許可權有限**：此原則會判斷您目錄中來賓的許可權。 選取 **[是]** 來封鎖特定目錄工作的訪客，例如列舉使用者、群組或其他目錄資源。 選取 [**否**]，為來賓提供與目錄中的一般使用者相同的目錄資料存取權。
     - **來賓 inviter 角色中的管理員和使用者可以邀請**：若要允許「來賓 inviter」角色中的系統管理員和使用者邀請客人，請將此原則設定為 **[是]**。
     - **成員可邀請**：若要允許您目錄中的非系統管理員成員邀請來賓，請將此原則設定為 [是]**** (建議使用)。 如果您希望只讓系統管理員新增來賓，可以將此原則設定為 [否]****。 請記住，設定為 [否]**** 將會限制非系統管理員小組擁有者的來賓體驗；他們只能在已由系統管理員在 AAD 中新增的 Teams 中新增來賓。
     - **客人可以邀請**：若要讓客人邀請其他客人，請將此原則設定為 **[是]**。
         > [!IMPORTANT]
         > Teams 目前不支援來賓邀請者角色，因此，即使您將 **[來賓可邀請]** 設定為 **[是]**，來賓仍無法在 Teams 中邀請其他來賓。
     - **啟用電子郵件的一次性密碼（預覽版）**：如需一次性密碼功能的詳細資訊，請參閱[電子郵件一次性密碼驗證（預覽版）](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)。
     - 共同作業**限制**：如需有關允許或封鎖特定網域之邀請的詳細資訊，請參閱[允許或封鎖來自特定組織的 B2B 使用者邀請](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。
        > [!NOTE]
        > 如需共同作業限制，請參閱[啟用 B2B 外部共同作業和管理可邀請來賓的人員](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。

    如需有關控制誰可以邀請來賓的詳細資訊，請參閱[委派 Azure Active Directory B2B 共同作業邀請](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。

## <a name="step-3-configure-microsoft-365-groups"></a>步驟3：設定 Microsoft 365 群組

1. 在 Microsoft 365 系統管理中心中，移至 [**設定**  >  **組織設定**]，按一下 [**服務**]，然後選取 [ **Microsoft 365 群組**]。

     ![螢幕擷取畫面顯示 Microsoft 365 群組設定](media/guest-access-checklist-services-settings.png)
2. 確認已選取 [**允許組織存取群組內容外的群組成員**] 核取方塊。 如果未選取此設定，來賓將無法存取任何群組內容。

    ![螢幕擷取畫面顯示 Microsoft 365 群組設定](media/guest-access-checklist-office365.png)
3. 確認已選取 [**允許群組擁有者將組織外的人員新增至群組**] 核取方塊。 如果未選取此設定，小組擁有者將無法新增來賓。 此設定至少必須開啟才能支援來賓存取。

如需設定這些設定的詳細指示，請參閱[管理 microsoft 365 群組中的來賓存取](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)及[控制 microsoft 365 群組中的來賓存取權](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups)。

## <a name="step-4-configure-sharing-in-microsoft-365"></a>步驟4：在 Microsoft 365 中設定共用

請確定使用者可以新增來賓。 做法如下：

1. 在 Microsoft 365 系統管理中心中，移至 [**設定**  >  **組織設定**]，按一下 [**安全性 & 隱私權**]，然後選取 [**共用**]。

     ![螢幕擷取畫面顯示服務設定的範例](media/guest-access-checklist-security-privacy-settings.png)

2. 選取 [**允許使用者將新的來賓新增至此組織**] 核取方塊，然後按一下 [**儲存變更**]。

     ![螢幕擷取畫面顯示共用設定切換的範例](media/guest-access-checklist-sharing-setting.png)

    > [!NOTE]
    > 這個設定相當於 Azure AD 中的 [**使用者設定**] 中的 [**成員可以邀請**] 設定  >  **External users** 。  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a>步驟5：驗證 SharePoint 中的共用設定

1. 登入 Microsoft 365 系統管理中心。
2. 選取 [系統**管理中心**] 底下的 [ **SharePoint**]。
3. 在新的 SharePoint 系統管理中心的 [**網站**] 底下，選取 [作用中的**網站**]。

    ![SharePoint 系統管理中心的作用中網站](media/guest-access-checklist-SPOSettings0.png)

3. 選取網站，然後按一下 [**共用**]。
4. 確定該選項已設定為 [**任何人**] 或 [**現有來賓**]。

     ![螢幕擷取畫面顯示 SharePoint Online 設定切換開關的範例](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a>步驟6：設定來賓使用者許可權

在團隊應用程式的個別小組層級，設定來賓許可權來控制來賓是否可以建立、更新或刪除頻道。 小組管理員和小組擁有者可以設定這些設定。

![螢幕擷取畫面顯示 [團隊/頻道設定] 切換開關的範例](media/guest-access-checklist-TeamsSettings2.png)

若要深入瞭解來賓存取，請參閱[小組中的來賓存取權](guest-access.md)及[開啟或關閉 Microsoft 團隊的來賓存取權](set-up-guests.md)。

## <a name="troubleshooting"></a>疑難排解

如果您在設定來賓存取或在小組中新增來賓時遇到問題，請使用下列資源來協助您：

[針對 Microsoft Teams 中的來賓存取問題進行疑難排解](troubleshoot-guest-access.md)

[團隊疑難排解](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
