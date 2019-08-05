---
title: Skype 室系統信任的網域
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: 請閱讀本主題, 瞭解如何針對 Skype 會議室系統和商務用 Skype 設定受信任的網域。
ms.openlocfilehash: eacc468508ba9107534ce4ac729edf0d0d6c895d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190990"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="97327-103">Skype 室系統信任的網域</span><span class="sxs-lookup"><span data-stu-id="97327-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="97327-104">請閱讀本主題, 瞭解如何針對 Skype 會議室系統和商務用 Skype 設定受信任的網域。</span><span class="sxs-lookup"><span data-stu-id="97327-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="97327-105">受信任的網域</span><span class="sxs-lookup"><span data-stu-id="97327-105">Trusted domains</span></span>

<span data-ttu-id="97327-106">商務用 Skype 用戶端會顯示一個對話方塊, 讓使用者從商務用 Skype 伺服器接受憑證 (如果登入的使用者帳戶的 SIP 網域與憑證上的 Subject 或 Subject 替換名稱中所顯示的名稱不同)。</span><span class="sxs-lookup"><span data-stu-id="97327-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="97327-107">如果針對貴組織中的商務用 Skype Server 所設定的憑證沒有 Subject 或 Subject 替換名稱中的 Skype 會議室系統帳戶的 SIP 功能變數名稱, 您必須設定在信任網域下的憑證上顯示的那些網域。Skype 聊天室系統主控台電腦上的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="97327-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="97327-108">您的 Skype 會議室系統製造商-提供的 Skype 會議室系統管理員指南說明如何在商務用 Skype 用戶端中新增受信任網域的方式和位置。</span><span class="sxs-lookup"><span data-stu-id="97327-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="97327-109">例如, 假設在商務用 Skype 伺服器上設定的憑證具有 [CONTOSO] 的主體/Subject 替換名稱。[本機], 而指派給使用者的其中一個 SIP 網域是「confrm1@contoso.net」。</span><span class="sxs-lookup"><span data-stu-id="97327-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="97327-110">因為 contoso.net 不在憑證中, 所以在 Skype 會議室系統電腦上, 您需要將「contoso. local」設定為在登錄中受信任的網域, 如 Skype 會議室系統製造商提供的 Skype 會議室系統管理員指南中所述。</span><span class="sxs-lookup"><span data-stu-id="97327-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

