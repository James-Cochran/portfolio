## Type of Change
- [ X ] feature ⛲
- [ X ] documentation update 📃
- [ X ] testing 🧪
<!--- Delete any above that do not apply to this PR -->

## Description
This PR adds the ability to delete a company for a user through the DELETE /api/v1/users/:userid/companies/:id endpoint.

When a company is deleted, any associated job applications are also removed, while contacts remain intact.

I commented out strict: true in the CompaniesController Rolify call. Wally  and I believe this was mistakenly included. After reviewing the Rolify documentation, we found no reason for its presence in this controller. All tests still pass with it commented out.

Documentation in the README was updated for this endpoint.

Tests were written for successful and unsuccessful requests (unauthorized access, non-existent company).

## Motivation and Context
This change was required to allow users to remove companies they no longer need while maintaining data integrity by keeping contacts but removing job applications.

## Related Tickets
closes #70 https://github.com/turingschool/tracker-crm/issues/70

## Added Test?
- [ X ] Yes 🫡
  - Request / Controller Tests
  - Model Tests
  - Policy Tests
- [ ] No 🙅
- [ X ] All previous tests still pass 🥳

## Checklist:
- [ X ] My code follows the code style of this project.
- [ X ] My change requires a change to the documentation.
- [ X ] I have updated the documentation accordingly.
- [ ] This PR includes a Migration and I have notified the deployment team and PM so they can run the migration after the PR is merged.