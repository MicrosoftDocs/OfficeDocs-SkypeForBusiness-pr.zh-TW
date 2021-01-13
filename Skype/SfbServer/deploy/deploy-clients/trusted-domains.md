---
title: Skype 室系統信任的網域
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: 閱讀此主題以瞭解如何為 Skype 會議室系統和商務用 Skype 設定信任的網域。
ms.openlocfilehash: c7883ed0cbc2e805ee0ba3cddfb3b2cee1163c35
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834113"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="defa1-103">Skype 室系統信任的網域</span><span class="sxs-lookup"><span data-stu-id="defa1-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="defa1-104">閱讀此主題以瞭解如何為 Skype 會議室系統和商務用 Skype 設定信任的網域。</span><span class="sxs-lookup"><span data-stu-id="defa1-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="defa1-105">信任的網域</span><span class="sxs-lookup"><span data-stu-id="defa1-105">Trusted domains</span></span>

<span data-ttu-id="defa1-106">商務用 Skype 用戶端會顯示一個對話方塊，可讓使用者在登入的使用者帳戶的 SIP 網域與憑證上的主語或主體替代名稱中所呈現的名稱不同時，接受來自商務用 Skype 伺服器的憑證。</span><span class="sxs-lookup"><span data-stu-id="defa1-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="defa1-107">如果為組織中的商務用 Skype 伺服器設定的憑證沒有以主旨或主體替代名稱顯示的 Skype 會議室系統帳戶的 SIP 功能變數名稱，您必須在商務用 Skype 系統主控台機器上，設定 [信任的網域] 登錄機碼底下的憑證所呈現的網域。</span><span class="sxs-lookup"><span data-stu-id="defa1-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="defa1-108">您的 Skype 會議室系統製造商-提供的 skype 會議室系統管理員指南說明如何在商務用 Skype 用戶端中新增信任的網域。</span><span class="sxs-lookup"><span data-stu-id="defa1-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="defa1-109">例如，假設在商務用 Skype Server 上設定的憑證具有「CONTOSO」的主體/主體替代名稱。LOCAL "和指派給使用者之 Skype 會議室系統登入位址的其中一個 SIP 網域為" confrm1@contoso.net "。</span><span class="sxs-lookup"><span data-stu-id="defa1-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="defa1-110">由於 contoso.net 不在憑證中，在 Skype 聊天室系統電腦上，您必須將 "contoso" 設定為登錄中的信任網域，如您的 Skype 會議室系統製造商提供的 skype 會議室系統管理員指南所述。</span><span class="sxs-lookup"><span data-stu-id="defa1-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

