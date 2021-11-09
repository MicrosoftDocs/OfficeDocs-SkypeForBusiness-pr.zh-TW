---
title: 新增前端伺服器組合 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: 以 Enterprise Edition 部署而言，您可以將音訊/視訊會議服務、中繼伺服器或兩者都組合在前端集區上，或者，也可以將每一項各自部署為獨立伺服器。以 Standard Edition Server 部署而言，如果啟用會議，則一律會組合音訊/視訊會議服務。
ms.openlocfilehash: e4f7186ab036ca0d4f3cdaad02ac47b8dbb4b362
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860420"
---
# <a name="add-front-end-server-collocations-2010"></a>新增前端伺服器組合 2010

以 Enterprise Edition 部署而言，您可以將音訊/視訊會議服務、中繼伺服器或兩者都組合在前端集區上，或者，也可以將每一項各自部署為獨立伺服器。以 Standard Edition Server 部署而言，如果啟用會議，則一律會組合音訊/視訊會議服務。

> [!NOTE]
> 如果在「選取功能」頁面上選取 [會議]，則需要音訊/視訊會議服務。Enterprise Edition 前端集區可以使用組合的音訊/視訊會議服務或獨立 A/V 會議集區。如果未選取 [會議]，則無法使用 [組合音訊/視訊會議服務]。

您可以在 Standard Edition 前端伺服器或 Enterprise Edition 前端集區上組合中繼伺服器角色。 如果您對支援媒體旁路和網域名稱系統 (DNS) 負載平衡的合格公用交換電話網路 (PSTN) 閘道部署了直接 SIP 連線，就不需要獨立的中繼伺服器集區。 因為合格閘道能夠將 DNS 負載平均分攤到中繼伺服器集區中，讓後者接收集區裡任何中繼伺服器的流量。 此外，當您已部署 IP-PBXs 或連線至網際網路電話語音伺服器提供者的會話邊界控制器 (SBC) 時，建議您在前端集區上組合轉送伺服器，只要符合下列任一條件：

- IP-PBX 或 SBC 設定為接收集區中任何中繼伺服器的流量，並一律將流量傳送至集區中的所有中繼服務器。

- IP-PBX 或 SBC 設定為接收集區中任何中繼伺服器的流量，並一律將流量傳送至集區中的所有中繼服務器。

您可以使用 Microsoft Lync Server 2013，規劃工具評估您想要組合轉送伺服器的前端集區是否可以處理負載。 如果環境無法符合這些需求，則您必須部署獨立的中繼伺服器集區。

一般來說，如果您的組織具有高可用性和擴充性，組合的 A/V 會議伺服器或轉送伺服器，則不建議使用 Enterprise Edition 部署中的前端集區中組合這些伺服器角色的詳細資訊，請參閱部署檔中的[定義和設定前端集](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)區。 如需 A/V 會議功能和元件的詳細資訊，請參閱規劃文件中的＜[Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing)＞。 如需企業語音功能和元件（包括轉送伺服器）的詳細資訊，請參閱規劃檔中的[Plan for 企業語音 in 商務用 Skype Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) 。