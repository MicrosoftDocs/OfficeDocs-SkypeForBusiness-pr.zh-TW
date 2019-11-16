---
title: 使用新式驗證登入 Microsoft 團隊
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 如何使用新式驗證登入 Microsoft 團隊。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5698058cbfecd62f92cfe9f198657f7c280deff
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "37568681"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>使用新式驗證登入 Microsoft 團隊
==========================

Microsoft 團隊使用新式驗證來輕鬆且安全地保持登入體驗。 若要查看使用者如何登入小組，請閱讀登[入小組](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)。

## <a name="how-modern-authentication-works"></a>新式驗證的運作方式

新式驗證是一個可讓團隊知道使用者已在其他位置輸入其認證（例如其公司電子郵件和密碼）的程式，因此不需要再次輸入它們即可啟動 app。 體驗會根據幾個因素而有所不同，就像使用者是在 Windows 或在 Mac 上運作一樣。 根據您的組織是否已啟用單一要素驗證或多重要素驗證（多重要素驗證），它也會根據您的組織，提供唯一的程式碼、輸入 PIN，或呈現指紋）。 以下是每個新式驗證案例的結尾。

### <a name="windows-users"></a>Windows 使用者 

- 如果使用者已透過其 Office 365 企業帳戶登入其他 Office 應用程式，當他們啟動團隊時，他們會直接移至應用程式。 您不需要他們輸入其認證。

- 如果使用者未在其他位置登入 Office 365 企業版帳戶，當他們開始團隊時，系統會要求他們提供單一要素或多重要素驗證（SFA 或 MFA），這取決於貴組織決定要需要處理的程式。

- 如果使用者已登入加入網域的電腦，當他們啟動團隊時，可能會要求您執行一個更驗證步驟，視貴組織選擇要要求 MFA 或其電腦是否已需要 MFA 登入而定。 如果他們的電腦已要求 MFA 登入，當他們開啟 [小組] 時，應用程式就會自動啟動。

### <a name="mac-users"></a>Mac 使用者 

當使用者開始團隊時，其電腦將無法從其 Office 365 企業版帳戶或其他任何 Office 應用程式中提取其認證。 相反地，他們會看到要求他們進行 SFA 或 MFA 的提示（視貴組織的設定而定）。 使用者輸入其認證之後，就不需要再提供這些認證。 從該點開始，團隊會在他們在同一部電腦上工作時自動啟動。

## <a name="switching-accounts-after-completing-modern-authentication"></a>完成新式驗證之後切換帳戶

如果使用者是在加入網域的電腦上工作（例如，如果其租使用者已啟用 Kerberos），則他們在完成新式驗證之後，就無法切換使用者帳戶。 如果使用者無法在加入網域的電腦上工作，他們可以切換帳戶。

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>在完成新式驗證後登出 Microsoft 團隊
若要登出團隊，使用者可以按一下應用程式頂端的個人檔案圖片，**然後選取 [登出]**。他們也可以在其工作列中以滑鼠右鍵按一下應用程式圖示，然後選取 [**登出**]。登出團隊之後，他們需要再次輸入其認證，才能啟動 app。

## <a name="troubleshooting-modern-authentication"></a>現代驗證疑難排解

每個使用團隊的組織都能使用新式驗證，所以如果使用者無法完成程式，您的網域或貴組織的 Office 365 企業版帳戶可能會有問題。 

如需詳細資訊，請參閱[為什麼我無法登入 Microsoft 團隊？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)。

