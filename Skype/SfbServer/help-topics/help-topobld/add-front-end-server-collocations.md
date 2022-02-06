---
title: 新增前端伺服器組合
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: 以 Enterprise Edition 部署而言，音訊/視訊會議服務是在前端集區上組合。您也可以在前端集區上組合中繼伺服器，或將其部署為獨立伺服器。如果啟用會議，則一律會組合音訊/視訊會議服務。
---

# <a name="add-front-end-server-collocations"></a>新增前端伺服器組合

以 Enterprise Edition 部署而言，音訊/視訊會議服務是在前端集區上組合。您也可以在前端集區上組合中繼伺服器，或將其部署為獨立伺服器。如果啟用會議，則一律會組合音訊/視訊會議服務。

> [!NOTE]
> 如果在「選取功能」頁面上選取 [會議]，則需要音訊/視訊會議服務。Enterprise Edition 前端集區使用組合的音訊/視訊會議服務。如果未選取 [會議]，則無法使用 [組合音訊/視訊會議服務]。

您可以在 Standard Edition 前端伺服器或 Enterprise Edition 前端集區上組合中繼伺服器角色。 如果您對支援媒體旁路和網域名稱系統 (DNS) 負載平衡的合格公用交換電話網路 (PSTN) 閘道部署了直接 SIP 連線，就不需要獨立的中繼伺服器集區。 因為合格閘道能夠將 DNS 負載平均分攤到中繼伺服器集區中，讓後者接收集區裡任何中繼伺服器的流量。 此外，當您已部署 IP-PBXs 或連線至網際網路電話語音伺服器提供者的會話邊界控制器 (SBC) 時，建議您在前端集區上組合轉送伺服器，只要符合下列任一條件：

- IP-PBX 或 SBC 設定為接收集區中任何中繼伺服器的流量，並一律將流量傳送至集區中的所有中繼服務器。

- IP-PBX 或 SBC 設定為接收集區中任何中繼伺服器的流量，並一律將流量傳送至集區中的所有中繼服務器。

您可以使用 Microsoft Lync Server 2013，規劃工具評估您想要組合轉送伺服器的前端集區是否可以處理負載。 如果環境無法符合這些需求，則您必須部署獨立的中繼伺服器集區。

一般而言，如果組織具有高可用性和延展性需求，則不建議組合中繼伺服器。 如需在 Enterprise Edition 部署中的前端集區中組合這些伺服器角色的詳細資訊，請參閱部署文件中的＜[Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)＞。 如需 A/V 會議功能和元件的詳細資訊，請參閱規劃文件中的＜[Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing)＞。 如需企業語音功能和元件（包括轉送伺服器）的詳細資訊，請參閱規劃檔中的[Plan for 企業語音 in 商務用 Skype Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) 。