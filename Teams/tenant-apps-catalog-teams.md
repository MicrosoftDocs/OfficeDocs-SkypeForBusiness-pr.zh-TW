---
title: 在 Microsoft 團隊租使用者應用程式目錄中發佈應用程式
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
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
ms.openlocfilehash: c1b2fb38dcca7142cad82d290b1225e69f035bae
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836913"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a>在 Microsoft 團隊租使用者應用程式目錄中發佈應用程式
=======================================================

您可以使用 Microsoft 團隊租使用者應用程式目錄來測試和發佈業務線應用程式至您的組織。

[團隊租使用者應用程式目錄] 可讓您散佈專為您的組織建立且您依賴來完成重要業務功能的業務線應用程式。

若要為您的組織發佈應用程式，請使用具有全域管理員或團隊服務管理員角色的帳戶登入您的小組用戶端，然後依照下列指示進行。

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a>在來自團隊用戶端的租使用者應用程式目錄中發佈應用程式

> [!NOTE]
> 您必須使用已啟用全域管理員或團隊服務管理員角色的帳戶登入 Microsoft 團隊用戶端，才能為您的組織發佈應用程式。 深入瞭解如何[使用系統管理員角色來管理團隊](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles)。

### <a name="get-a-teams-app-package"></a>取得團隊應用程式套件

團隊應用程式套件是使用[團隊 App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)建立的。 有了應用程式套件之後，您就可以將它新增至企業應用程式目錄。 雖然租使用者中的所有使用者都可以查看應用程式目錄，但只有全域管理員和團隊服務系統管理員具備發佈及管理的功能。

### <a name="go-to-the-tenant-apps-catalog"></a>移至租使用者應用程式目錄

啟動 Microsoft 團隊用戶端，然後使用您的全域或團隊服務管理員認證登入。 選取應用程式左側的 [**應用程式**]，然後選取名為 [您的特定組織] （在此範例中為 Contoso）的新節。 貴組織中的使用者可以在目錄中查看應用程式，並為他們所屬的小組安裝這些 app。

![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>將應用程式新增至租使用者應用程式目錄

1. 在 [**應用程式**] 頁面上，選取 **[上傳 Contoso 的自訂應用程式** > 上**傳**]。

    ![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image02.png)

    （您也可以選擇 [**上傳給我] 或 [我的小組**]，這稱為 [側*載*]。 [邊載] 可讓您的小組或您選取的小組使用該 app。

2. 流覽至該應用程式套件，選取它，然後按一下 [**開啟**]。

    ![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image03.png)

當您回到您的租使用者應用程式目錄時，新的企業 app 就會出現在該處。 請記住，只有您和貴組織的成員才能存取此應用程式目錄。

### <a name="update-an-app-in-the-tenant-apps-catalog"></a>更新租使用者應用程式目錄中的應用程式

1. 從您的租使用者應用程式目錄中，選取 "**...**" 在您要更新的應用程式右上方。

2. 流覽至已更新的應用程式套件，選取它，然後按一下 [**開啟**]。

    ![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image04.png)

App 將會修正為版本2.0。 您也可以從這個功能表刪除整個公司的 app。

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a>使用 Office 365 管理入口網站管理租使用者應用程式目錄

如果您的應用程式需要修正錯誤，您可以透過 Microsoft 365 系統管理中心暫時停用應用程式 **> 團隊系統管理中心** > **團隊 app** > **許可權原則** > <原則名稱（例如「全域（組織範圍的預設值）」） >**租**使用者 > 封鎖特定 app 並允許其他所有人，並將您的應用程式新增到清單中。

![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image05.png)

停用應用程式將會封鎖使用者與 app 的互動，而不需要徹底刪除 app。 當您在企業中管理 app 時，這些控制項可提供額外的靈活性和控制權。
