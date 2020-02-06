---
title: 憑證要求 (已傳回)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: '[線上憑證要求狀態] 頁面提供成功建立併發出線上憑證要求所產生的重要資訊。 此頁面提供可唯一識別憑證的憑證指紋。 根據預設，會選取 [將此憑證指派給商務用 Skype Server 認證用途] 核取方塊。 如果您按一下 [完成]，就會自動將憑證指派給 Lync Server 2013，目的是您在證書要求的建立步驟期間定義的用途。 根據預設，會指派證書的目的為：'
ms.openlocfilehash: 7b4ee3d615de0d0d58e041ba1860cc1cd2d34219
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823807"
---
# <a name="certificate-request-returned"></a>憑證要求 (已傳回)
 
[**線上憑證要求狀態**] 頁面提供成功建立併發出線上憑證要求所產生的重要資訊。 此頁面提供可唯一識別憑證的憑證指紋。 根據預設，會選取 [**將此憑證指派給商務用 Skype Server 認證用途**] 核取方塊。 如果您按一下 **[完成]**，就會自動將憑證指派給 Lync Server 2013，目的是您在證書要求的建立步驟期間定義的用途。 根據預設，會指派證書的目的為：
  
- 相互傳輸層安全性（MTLS）的伺服器預設值-與用戶端及其他伺服器的連線
    
- Web 服務內部-用於傳輸層安全性/安全通訊端層的內部 Web 服務網站上的用戶端和伺服器連線（TLS/SSL）
    
- 在適用于 TLS/SSL 的外部 Web services 網站上的 Web 服務外部用戶端與伺服器連線
    
按一下 [**查看憑證詳細資料**] 以查看憑證，以確認憑證的屬性是您想要的內容，且該憑證已準備就緒，可在伺服器上使用。
  
按一下 **[完成]** 以完成線上憑證申請程式。 如果您已選取 [**將此憑證指派給商務用 Skype Server 認證使用**方式] 核取方塊，則會自動指派證書。 如果您選擇清除此核取方塊，您必須以個別步驟指派證書。 
  
> [!IMPORTANT]
> 如果頒發憑證授權單位（CA）根憑證不在電腦的根信任憑證授權單位存放區中，或如果中間 CA 憑證不在適當的存放區中，您會看到 [摘要狀態]，如下列影像所示。 您沒有指派憑證的選項。 若要完成憑證指派程式，您必須匯入頒發 CA 根憑證及任何中間 CA 憑證，然後按一下 [主要憑證] 嚮導頁面上的 [**指派**]，指派憑證。
  

