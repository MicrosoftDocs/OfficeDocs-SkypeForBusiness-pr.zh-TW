---
title: 在 Microsoft 團隊系統管理中心管理您的應用程式
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 瞭解如何在 Microsoft 團隊系統管理中心的 [管理應用程式] 頁面上管理您的團隊應用程式
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 532129792dd35a2b016510094f1b08beade1b32a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136843"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>在 Microsoft 團隊系統管理中心管理您的應用程式
======================================================

做為管理員，Microsoft [團隊管理中心] 中的 [**管理應用**程式] 頁面是您在組織的應用程式目錄中查看和管理所有團隊應用程式的位置。 在這裡，您可以查看應用程式的組織層級狀態和屬性、將新的自訂應用程式上傳到您的租使用者應用程式目錄、封鎖或允許組織階層的應用程式，以及管理整個組織的應用程式設定。

[**管理應用程式**] 頁面可讓您查看租使用者目錄中所有可用的應用程式，為您提供所需的資訊，讓您決定要允許或封鎖整個組織的哪些應用程式。 接著，您可以使用[應用程式許可權原則](teams-app-permission-policies.md)、[應用程式設定原則](teams-app-setup-policies.md)，以及[自訂的 app 原則和設定](teams-custom-app-policies-and-settings.md)，為貴組織中的特定使用者設定 app 體驗。

在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > **管理應用程式**]。 您必須是全域系統管理員或團隊服務系統管理員，才能存取該頁面。

## <a name="view-apps-in-your-tenant-app-catalog"></a>在您的租使用者應用程式目錄中查看應用程式

您可以查看租使用者應用程式目錄中的每個應用程式，包括下列每個應用程式的相關資訊。

![[受管理的應用程式] 頁面的螢幕擷取畫面](media/manage-apps.png)

- **Name （名稱**）：應用程式名稱。 按一下應用程式名稱，查看該應用程式的詳細資訊。 這包括應用程式的描述、是否允許或封鎖、版本、套用至應用程式的類別、認證狀態、支援的功能，以及應用程式識別碼。 以下是一個範例：<br> 
![應用程式的 [應用程式詳細資料] 頁面的螢幕擷取畫面](media/manage-apps-app-details.png)
- **認證**：如果 app 已透過認證，您就會看到**Microsoft 365 認證**或**發行商認證**。 按一下連結以查看 app 的認證詳細資料。 如果您看到**--**「」，表示沒有 app 的認證資訊。 若要深入瞭解團隊中的認證應用程式，請參閱[Microsoft 365 App 認證計畫](https://docs.microsoft.com/teams-app-certification/all-apps)。  
- [**類別**]：適用于 app 的類別。
- **App 狀態**：組織階層的 app 狀態，可能是下列其中一項：
    - **允許**：應用程式可供貴組織中的所有使用者使用。
    - 已**封鎖**：應用程式遭到封鎖，且無法供貴組織中的任何使用者使用。<br>
請務必注意，此資料行代表原在**整個組織結構設定**窗格中之 app 的「允許」和「封鎖」狀態。 您現在可以在 [**管理應用程式**] 頁面上的整個組織結構中查看、封鎖及允許 app。 
- **版本**： App 版本。

若要在表格中查看您想要的資訊，請按一下右上角的 [**編輯欄**]，在表格中新增或移除欄。

## <a name="upload-a-new-app"></a>上傳新的應用程式

您可以使用您的 [應用程式目錄] 來測試及發佈專為貴組織建立的業務線應用程式。 團隊應用程式套件是使用[團隊 App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)建立的。 當您有應用程式套件時，您可以將它新增到您的 [應用程式目錄]。 雖然貴組織中的所有使用者都可以查看應用程式目錄，但只有全域管理員和團隊服務系統管理員可以發佈及管理它。

若要將新的自訂應用程式上傳到您的租使用者應用程式目錄，請按一下 **[上傳新應用程式**]，以 .zip 格式上傳您的 應用程式在上傳後不會醒目提示，因此您需要搜尋您的應用程式目錄來尋找它。

若要在上傳應用程式後進行更新，請在 [**管理應用**程式] 頁面上的應用程式清單中，按一下應用程式名稱，然後按一下 [**更新**]。 這麼做會取代應用程式目錄中的現有應用程式，以及所有應用程式許可權原則，以及 app 設定原則，都會針對更新的應用程式繼續執行。

若要深入瞭解，請參閱[在團隊中管理您的商務用應用程式](manage-your-lob-apps.md)。

## <a name="allow-and-block-apps"></a>允許及封鎖應用程式

[**管理應用程式**] 頁面是您在組織階層允許或封鎖個別 app 的位置。 它會顯示每個可用的 app 及其目前的組織層級 app 狀態。 （封鎖及允許組織階層的 app 已從**整個組織範圍的應用程式設定**窗格移至這裡。）

若要允許或封鎖應用程式，請選取它，然後按一下 [**允許**] 或 [**封鎖**]。 當您封鎖 app 時，所有與該 app 的互動都會停用，而且該 app 不會出現在小組中您組織中的任何使用者。

當您封鎖或允許 [**管理應用程式**] 頁面上的應用程式時，該應用程式會遭到封鎖，或您組織中的所有使用者都能使用該 app。  當您在小組 app 許可權原則中封鎖或允許應用程式時，系統會封鎖或允許指派該原則的使用者。 若要讓使用者能夠安裝任何 app 並與之互動，您必須在 [**管理應用程式**] 頁面上，或已指派給使用者的 app 許可權原則中，允許該應用程式位於組織層級。

## <a name="manage-org-wide-app-settings"></a>管理整個組織內的應用程式設定

使用整個組織的 app 設定來控制使用者是否可以安裝協力廠商應用程式，以及使用者是否可以上傳或與您組織中的自訂應用程式互動。 全組織式應用程式設定會控制所有使用者的行為，並覆寫指派給使用者的任何其他應用程式許可權原則。 您可以使用它們來控制惡意或有問題的 app。

1. 在 [**管理應用程式**] 頁面上，選取 [**全組織式應用程式設定**]。 接著，您可以在面板中設定您想要的設定。

    ![整個組織內的應用程式設定的螢幕擷取畫面](media/manage-apps-org-wide-app-settings.png)
    
2. 在**協力廠商應用程式**下，關閉或開啟這些設定以控制對協力廠商應用程式的存取：

    - **允許團隊中的協力廠商應用程式**：這可控制使用者是否可以使用協力廠商應用程式。 如果您關閉此設定，您的使用者將無法安裝或使用任何協力廠商應用程式。 針對您允許的應用程式，狀態會顯示為 [允許]，**但已停用整個組織**結構。              

        > [!NOTE]
        > 在 Microsoft 365 政府版團隊部署中，[**允許團隊中的協力廠商應用程式**] 設定預設為關閉。

        當 [**允許團隊中的協力廠商應用程式**關閉] 時，系統會停用[傳出 webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) ，這表示使用者無法建立。 當此設定為 [開啟] 時，無論使用者應用程式許可權原則中的設定為開啟或關閉，所有使用者都能啟用外寄 webhooks。
    - **允許預設發佈至商店的任何新的協力廠商應用程式**：這會控制發佈至 [小組] 應用程式商店的新的協力廠商應用程式是否會自動在小組中提供。 如果您允許協力廠商應用程式，則只能設定此選項。

3. 在 [**自訂應用程式**] 底下，關閉或開啟 [**允許與自訂應用程式互動**]。 這個設定控制使用者是否能與自訂 app 互動。 若要深入瞭解，請參閱[管理團隊中的自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)。
4. 按一下 [**儲存**以組織範圍內的應用程式設定] 生效。

## <a name="related-topics"></a>相關主題

- [在 Teams 中的應用程式系統管理設定](admin-settings.md)
