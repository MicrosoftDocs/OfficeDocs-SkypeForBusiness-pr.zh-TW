---
title: Lync Server 2010 的伺服器設定擴展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: '若要編輯此電腦的屬性, 請執行下列動作:'
ms.openlocfilehash: 28261b3637040acda70218f23101b4337b1f90c3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193019"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Lync Server 2010 的伺服器設定擴展器
 
若要編輯此電腦的屬性, 請執行下列動作:
  
- 編輯此電腦的**完整功能變數名稱 (FQDN)** 。 此專案必須符合在網域名稱系統 (DNS) 中定義的電腦名稱稱, 以及與此電腦相關聯之憑證的消費者備用名稱 (SAN) 或主旨名稱 (SN.EXE)。
    
- 選取下列其中一項:
    
    **使用所有已設定的 ip 位址**: 選取此專案即可使用電腦上所有已設定的 ip 位址。
    
    > [!IMPORTANT]
    > 如果電腦有多個 IP 位址, 您必須知道與此電腦關聯的服務會將所有服務的 IP 位址都使用。 如果偵聽伺服器或服務預期要通訊特定的 IP 位址和埠, 則服務可能無法讓最佳選取要監聽的 IP 位址。 
  
    **將服務使用限制為選取的 IP 位址**: 如果您想要針對此電腦將偵聽的**主要 ip 位址**定義特定 ip 位址, 以便與部署中其他電腦和池進行通訊, 請選取此選項。 針對特定 IP 位址定義**PSTN IP 位址**, 電腦與服務將偵聽通訊並傳送與已定義 PSTN 閘道或 IP PBX 的通訊。
    

