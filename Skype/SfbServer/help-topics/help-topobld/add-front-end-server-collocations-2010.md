---
title: 新增前端伺服器組合 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: 在企業版部署中，您可以 collocate A/V 會議服務、中繼伺服器或這兩者都在前端池上，或者您可以將每個伺服器都部署為獨立伺服器。 若是標準版伺服器部署，如果已啟用會議，A/V 會議服務就會一直 collocated。
ms.openlocfilehash: 4a488aeca543d95042f9dfeec860934f472b94c3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820835"
---
# <a name="add-front-end-server-collocations-2010"></a>新增前端伺服器組合 2010

在企業版部署中，您可以 collocate A/V 會議服務、中繼伺服器或這兩者都在前端池上，或者您可以將每個伺服器都部署為獨立伺服器。 若是標準版伺服器部署，如果已啟用會議，A/V 會議服務就會一直 collocated。

> [!NOTE]
> 如果在 [**選取功能**] 頁面上選取 [**會議**]，就必須有 A/V 會議服務。 企業版前端池可以使用 collocated A/V 會議服務或獨立的 A/V 會議池。 如果未選取 [會議]，將無法使用 Collocate A/V 會議服務。

您可以 collocate 標準版前端伺服器或企業版前端池的中繼伺服器角色。 如果您將直接 SIP 連線部署到支援媒體旁路和網域名稱系統（DNS）負載平衡的合格公用交換電話網絡（PSTN）閘道，則不需要獨立的中繼伺服器池。 不需要獨立的吸入式伺服器池，因為合格的閘道能夠將 DNS 負載平衡傳送到中繼伺服器的池中，而且可以從池中的任何中繼伺服器接收流量。 我們也建議您在已部署 IP Pbx 或連線至網際網路電話語音器提供者的會話邊界控制器（SBC）時，在前端池中 collocate 轉送伺服器，只要符合下列任何一個條件：

- IP PBX 或 SBC 已設定為從池中的任何中繼伺服器接收流量，並可將流量統一傳送給池中的所有中繼伺服器。

- IP PBX 或 SBC 已設定為從池中的任何中繼伺服器接收流量，並可將流量統一傳送給池中的所有中繼伺服器。

您可以使用 Microsoft Lync Server 2013、規劃工具來評估您要 collocate 中繼伺服器的前端池是否可以處理負載。 如果您的環境無法符合這些需求，則您必須部署獨立的中繼伺服器池。

一般來說，如果您的組織有高可用性和伸縮性，請不要使用 collocation/V 會議服務器或中繼伺服器在企業版部署的前端池中，請參閱在部署檔中[定義及設定前端池](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。 如需 A/V 會議功能與元件的詳細資料，請參閱規劃檔中的[會議規劃](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)。 如需企業語音功能與元件（包括轉送伺服器）的詳細資料，請參閱規劃檔中的[商務用 Skype Server 2015 中的企業語音規劃](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)。


