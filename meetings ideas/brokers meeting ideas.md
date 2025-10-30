---
tags:
  - brokers
---

- #### general ideas:
	- ordering and how to apply it with Custom APIView classes selectors
	- discuss compose services dependencies
	- Can we depend on celery.py instead of flower.py when working with flower container? (for MR. Hussein)

- #### discussion:
	- Is Notification model scalable, answer this question:
		How to send Notification to all users/admins/owners? (add reciever_type) ([Jira](https://virtualzonetec.atlassian.net/browse/BROKERS-429?atlOrigin=eyJpIjoiMmE2MDA0MzlmYzA4NDM2YTlkZTFhNDI4NWRiYmE2MjkiLCJwIjoiaiJ9)) (second phase)
	- Is Notifications URL re-direct the client correctly to the same property on mobile app? ([Jira](https://virtualzonetec.atlassian.net/browse/BROKERS-376?atlOrigin=eyJpIjoiZGM1M2MzNDU3ZGQxNDgzM2ExOWY0MDgwNGJkMjM1NDYiLCJwIjoiaiJ9))
	- Add animation to search or filtering when waiting. ([Jira](https://virtualzonetec.atlassian.net/browse/BROKERS-460?atlOrigin=eyJpIjoiZjIzYWZjNmI4NTNhNGJhMWI0MTAxZDVhNTZhODdmMjUiLCJwIjoiaiJ9)) (second phase)
	- How to synchronize between Database payment record and payment result when server/database is down? ([Jira](https://virtualzonetec.atlassian.net/browse/BROKERS-371?atlOrigin=eyJpIjoiNGZkOTAzN2I4Y2VlNDQ3NWFiZjQzZjMwMGY4N2M4NTYiLCJwIjoiaiJ9))
	- What About neighborhood model idea (after regions and governorates)? ([Jira](https://virtualzonetec.atlassian.net/browse/BROKERS-270?atlOrigin=eyJpIjoiNTA3YmU0MDBjZmM2NGZkMjhmZDI0Y2MyZWZiZjIwYTMiLCJwIjoiaiJ9)) (second idea)
	- How to secure our project? (second phase)
		- Following security best practices
		- No id in JSON response