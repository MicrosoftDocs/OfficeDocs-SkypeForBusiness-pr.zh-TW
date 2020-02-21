---
title: 在 Microsoft 團隊租使用者應用程式目錄中發佈應用程式
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: 在 Microsoft 團隊租使用者應用程式目錄中發佈 app 的指導方針。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161612"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a>在 Microsoft 團隊租使用者應用程式目錄中發佈應用程式
=======================================================

您可以使用 Microsoft 團隊租使用者應用程式目錄來測試和發佈業務線應用程式至您的組織。

[團隊租使用者] 應用程式目錄可讓您散佈專為您的組織建立且您依賴來完成重要業務功能的業務線應用程式。

若要為您的組織發佈應用程式，請使用具有全域管理員或團隊服務管理員角色的帳戶登入團隊用戶端，然後遵循下列步驟。

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a>在來自團隊用戶端的租使用者應用程式目錄中發佈應用程式

> [!NOTE]
> 這些步驟說明如何使用 [團隊用戶端] 發佈應用程式。 您也可以在 Microsoft 團隊系統管理中心的 [**管理應用程式**] 頁面上發佈應用程式。 若要深入瞭解，請參閱[管理團隊中的應用程式](manage-apps.md)。

### <a name="get-a-teams-app-package"></a>取得團隊應用程式套件

團隊應用程式套件是使用[團隊 App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)建立的。 有了應用程式套件之後，您就可以將它新增到租使用者應用程式目錄中。 雖然貴組織中的所有使用者都可以查看應用程式目錄，但只有全域管理員和團隊服務管理員具備發佈及管理該功能的能力。

### <a name="go-to-the-tenant-app-catalog"></a>移至租使用者應用程式目錄

啟動團隊並使用您的全域或團隊服務管理員認證登入。 選取應用程式左側的 [**應用程式**]，然後選取名為 [您的特定組織] （在此範例中為 Contoso）的新節。 貴組織中的使用者可以在目錄中查看應用程式，並為他們所屬的小組安裝這些 app。

![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a>將應用程式新增至租使用者應用程式目錄

1. 在 [**應用程式**] 頁面上，選取 **[上傳 Contoso 的自訂應用程式** > 上**傳**]。

    ![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image02.png)

    （您也可以選擇 [**上傳給我] 或 [我的小組**]，這稱為 [側*載*]。 [邊載] 可讓您的小組或您選取的小組使用該 app。

2. 流覽至該應用程式套件，選取它，然後按一下 [**開啟**]。

    ![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image03.png)

當您回到您的租使用者應用程式目錄時，新的企業 app 就會出現在該處。 請記住，只有您和貴組織的成員才能存取此應用程式目錄。

### <a name="update-an-app-in-the-tenant-app-catalog"></a>在租使用者應用程式目錄中更新應用程式

1. 從您的租使用者應用程式目錄中，選取 "**...**" 在您要更新的應用程式右上方。

2. 流覽至已更新的應用程式套件，選取它，然後按一下 [**開啟**]。

    ![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image04.png)

App 將會修正為版本2.0。 您也可以從這個功能表刪除整個公司的 app。

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a>使用 Microsoft 團隊系統管理中心來管理租使用者應用程式目錄

如果您的應用程式需要修正錯誤，您可以暫時停用應用程式許可權原則中的使用者 app。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > ]**許可權原則**。
2. 選取您要編輯的 app 許可權原則，然後按一下 [**編輯**]。
3. 在 [**租使用者應用程式**] 底下，選取 [**封鎖特定的 app 並允許所有其他 app**]，然後新增您想要封鎖的 app。

停用 app 會封鎖使用者與 app 的互動，而不需要徹底刪除 app。 當您管理組織中的 app 時，這些控制項可提供額外的靈活性與控制權。

若要深入瞭解，請參閱[在團隊中管理 app 許可權原則](teams-app-permission-policies.md)。